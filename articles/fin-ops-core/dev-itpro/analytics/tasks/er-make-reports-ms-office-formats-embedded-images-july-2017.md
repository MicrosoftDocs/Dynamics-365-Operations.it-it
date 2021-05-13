---
title: Progettare le configurazioni per generare report in formato di Office con immagini incorporate
description: Questo argomento descrive come progettare configurazioni che generano documenti elettronici nei formati Excel e Word contenenti le immagini incorporate.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944559"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="6912f-103">Progettare le configurazioni per generare report in formato di Office con immagini incorporate</span><span class="sxs-lookup"><span data-stu-id="6912f-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6912f-104">Per completare i passaggi in questa procedura, prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="6912f-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="6912f-105">In questa procedura viene illustrato come progettare le configurazioni ER per generare un documento di Microsoft Excel o Word contenente le immagini incorporate.</span><span class="sxs-lookup"><span data-stu-id="6912f-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="6912f-106">In questa procedura, verranno create le configurazioni ER necessarie per la società di esempio, Litware, Inc. Questi passaggi possono essere completati mediante il set di dati USMF.</span><span class="sxs-lookup"><span data-stu-id="6912f-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="6912f-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6912f-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="6912f-108">Prima di inziare scaricare e salvare i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="6912f-108">Before you begin, download and save the following files:</span></span> 

| <span data-ttu-id="6912f-109">descrizione</span><span class="sxs-lookup"><span data-stu-id="6912f-109">Description</span></span>                                          | <span data-ttu-id="6912f-110">Nome file</span><span class="sxs-lookup"><span data-stu-id="6912f-110">File name</span></span>                   |
|------------------------------------------------------|-----------------------------|
| <span data-ttu-id="6912f-111">Configurazione del modello di dati ER</span><span class="sxs-lookup"><span data-stu-id="6912f-111">ER data model configuration</span></span>                          | [<span data-ttu-id="6912f-112">Model for cheques.xml</span><span class="sxs-lookup"><span data-stu-id="6912f-112">Model for cheques.xml</span></span>](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| <span data-ttu-id="6912f-113">Configurazione di formato ER</span><span class="sxs-lookup"><span data-stu-id="6912f-113">ER format configuration</span></span>                              | [<span data-ttu-id="6912f-114">Cheques printing format.xml</span><span class="sxs-lookup"><span data-stu-id="6912f-114">Cheques printing format.xml</span></span>](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| <span data-ttu-id="6912f-115">Immagine del logo dell'azienda</span><span class="sxs-lookup"><span data-stu-id="6912f-115">Company logo image</span></span>                                   | [<span data-ttu-id="6912f-116">Company logo.png</span><span class="sxs-lookup"><span data-stu-id="6912f-116">Company logo.png</span></span>](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| <span data-ttu-id="6912f-117">Immagine della firma</span><span class="sxs-lookup"><span data-stu-id="6912f-117">Signature image</span></span>                                      | [<span data-ttu-id="6912f-118">Signature image.png</span><span class="sxs-lookup"><span data-stu-id="6912f-118">Signature image.png</span></span>](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| <span data-ttu-id="6912f-119">Immagine della firma alternativa</span><span class="sxs-lookup"><span data-stu-id="6912f-119">Alternative signature image</span></span>                          | [<span data-ttu-id="6912f-120">Signature image 2.png</span><span class="sxs-lookup"><span data-stu-id="6912f-120">Signature image 2.png</span></span>](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| <span data-ttu-id="6912f-121">Modello di Microsoft Word per la stampa di assegni di pagamento</span><span class="sxs-lookup"><span data-stu-id="6912f-121">Microsoft Word template for printing payment checks</span></span>  | [<span data-ttu-id="6912f-122">Cheque template Word.docx</span><span class="sxs-lookup"><span data-stu-id="6912f-122">Cheque template Word.docx</span></span>](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a><span data-ttu-id="6912f-123">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6912f-123">Verify prerequisites</span></span>  
 1. <span data-ttu-id="6912f-124">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6912f-124">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="6912f-125">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="6912f-125">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="6912f-126">Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="6912f-126">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="6912f-127">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="6912f-127">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="6912f-128">Aggiungere una nuova configurazione del modello ER</span><span class="sxs-lookup"><span data-stu-id="6912f-128">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="6912f-129">Anziché creare un nuovo modello, è possibile caricare il file di configurazione del modello ER (Model for cheques.xml) salvato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6912f-129">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="6912f-130">Questo file contiene il modello dati di esempio per gli assegni di pagamento e il mapping del modello dati ai dati componenti dell'applicazione Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="6912f-130">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="6912f-131">Nella scheda dettaglio Versioni fare clic su Scambia.</span><span class="sxs-lookup"><span data-stu-id="6912f-131">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="6912f-132">Fare clic su Carica da file XML.</span><span class="sxs-lookup"><span data-stu-id="6912f-132">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="6912f-133">Fare clic su Sfoglia quindi selezionare Model for cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="6912f-133">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="6912f-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6912f-134">Click OK.</span></span>  
 6. <span data-ttu-id="6912f-135">Il modello caricato verrà utilizzato come origine dati delle informazioni per generare i documenti contenenti le immagini in Excel e Word.</span><span class="sxs-lookup"><span data-stu-id="6912f-135">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="6912f-136">Aggiungere una nuova configurazione di formato ER</span><span class="sxs-lookup"><span data-stu-id="6912f-136">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="6912f-137">Anziché creare un nuovo formato, è possibile caricare il file di configurazione del formato ER (Cheques printing format.xml) salvato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6912f-137">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="6912f-138">Questo file contiene il layout di esempio del formato per stampare gli assegni utilizzando il modulo prestampato e il mapping di questo formato al modello di dati per assegni.</span><span class="sxs-lookup"><span data-stu-id="6912f-138">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="6912f-139">Fare clic su Scambia.</span><span class="sxs-lookup"><span data-stu-id="6912f-139">Click Exchange.</span></span>  
 3. <span data-ttu-id="6912f-140">Fare clic su Carica da file XML.</span><span class="sxs-lookup"><span data-stu-id="6912f-140">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="6912f-141">Fare clic su Sfoglia e selezionare il file Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="6912f-141">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="6912f-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6912f-142">Click OK.</span></span>  
 6. <span data-ttu-id="6912f-143">Nella struttura espandere "Model for cheques".</span><span class="sxs-lookup"><span data-stu-id="6912f-143">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="6912f-144">Nella struttura selezionare "Model for cheques\Cheques printing format".</span><span class="sxs-lookup"><span data-stu-id="6912f-144">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="6912f-145">Il formato caricato verrà utilizzato per generare i documenti contenenti le immagini in Excel e Word.</span><span class="sxs-lookup"><span data-stu-id="6912f-145">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="6912f-146">Configurare i parametri utente ER</span><span class="sxs-lookup"><span data-stu-id="6912f-146">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="6912f-147">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="6912f-147">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="6912f-148">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="6912f-148">Click User parameters.</span></span>  
 3. <span data-ttu-id="6912f-149">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6912f-149">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="6912f-150">Attivare il flag "Esegui bozza" per avviare la versione bozza del formato selezionato anziché di quello completato.</span><span class="sxs-lookup"><span data-stu-id="6912f-150">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="6912f-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6912f-151">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="6912f-152">Configurare i Parametri di gestione cassa e banche</span><span class="sxs-lookup"><span data-stu-id="6912f-152">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="6912f-153">Andare a Gestione cassa e banche > Conti bancari > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="6912f-153">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="6912f-154">Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="6912f-154">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="6912f-155">Nel riquadro azioni, fare clic su Imposta.</span><span class="sxs-lookup"><span data-stu-id="6912f-155">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="6912f-156">Fare clic su Verifica.</span><span class="sxs-lookup"><span data-stu-id="6912f-156">Click Check.</span></span>  
 5. <span data-ttu-id="6912f-157">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="6912f-157">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="6912f-158">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="6912f-158">Click Edit.</span></span>  
 7. <span data-ttu-id="6912f-159">Selezionare Sì nel campo Logo società.</span><span class="sxs-lookup"><span data-stu-id="6912f-159">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="6912f-160">Fare clic su il logo della società.</span><span class="sxs-lookup"><span data-stu-id="6912f-160">Click Company logo.</span></span>  
 9. <span data-ttu-id="6912f-161">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="6912f-161">Click Change.</span></span>  
 10. <span data-ttu-id="6912f-162">Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="6912f-162">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="6912f-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6912f-163">Click Save.</span></span>  
 12. <span data-ttu-id="6912f-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6912f-164">Close the page.</span></span>  
 13. <span data-ttu-id="6912f-165">Espandere la sezione Firma.</span><span class="sxs-lookup"><span data-stu-id="6912f-165">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="6912f-166">Selezionare Sì nel campo Stampa prima firma.</span><span class="sxs-lookup"><span data-stu-id="6912f-166">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="6912f-167">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="6912f-167">Click Change.</span></span>  
 16. <span data-ttu-id="6912f-168">Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="6912f-168">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="6912f-169">Espandere la sezione Copie.</span><span class="sxs-lookup"><span data-stu-id="6912f-169">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="6912f-170">Nel campo Filigrana selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="6912f-170">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="6912f-171">Selezionare Sì nel campo Formato esportazione elettronica generica.</span><span class="sxs-lookup"><span data-stu-id="6912f-171">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="6912f-172">Selezionare la configurazione 'Cheques printing format'.</span><span class="sxs-lookup"><span data-stu-id="6912f-172">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="6912f-173">Ora il formato ER selezionato verrà utilizzato per la stampa degli assegni.</span><span class="sxs-lookup"><span data-stu-id="6912f-173">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="6912f-174">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="6912f-174">Click Attach.</span></span>  
 23. <span data-ttu-id="6912f-175">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="6912f-175">Click New.</span></span>  
 24. <span data-ttu-id="6912f-176">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="6912f-176">Click File.</span></span>  
 25. <span data-ttu-id="6912f-177">Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="6912f-177">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="6912f-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6912f-178">Close the page.</span></span>  
 27. <span data-ttu-id="6912f-179">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6912f-179">Close the page.</span></span>  
 28. <span data-ttu-id="6912f-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6912f-180">Close the page.</span></span>  
 29. <span data-ttu-id="6912f-181">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="6912f-181">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="6912f-182">Selezionare Sì nel campo Consenti creazione notifica anticipata su conti bancari inattivi.</span><span class="sxs-lookup"><span data-stu-id="6912f-182">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="6912f-183">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6912f-183">Click Save.</span></span>  
 32. <span data-ttu-id="6912f-184">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6912f-184">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
