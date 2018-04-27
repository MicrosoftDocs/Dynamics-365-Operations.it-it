--- 
title: Verificare le configurazioni per creare i report nei formati Microsoft Office con immagini incorporate
description: "Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività \"ER Creare report in formati di Microsoft Office con immagini incluse (Parte 1: Generare i report)\"."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe58809c60fa27a605d84a61893ff569ded058ef
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="review-configurations-to-make-reports-in-microsoft-office-formats-with-embedded-images"></a><span data-ttu-id="455f4-103">Verificare le configurazioni per creare i report nei formati Microsoft Office con immagini incorporate</span><span class="sxs-lookup"><span data-stu-id="455f4-103">Review configurations to make reports in Microsoft Office formats with embedded images</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="455f4-104">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività "ER Creare report in formati di Microsoft Office con immagini incluse (Parte 1: Generare i report)".</span><span class="sxs-lookup"><span data-stu-id="455f4-104">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 1: Set up parameters)” task guide.</span></span>

<span data-ttu-id="455f4-105">In questa procedura viene illustrato come progettare le configurazioni ER per generare i documenti elettronici contenenti le immagini incorporate in Microsoft Excel e Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="455f4-105">This procedure shows how to design Electronic reporting (ER) configurations to generate electronic documents that contain embedded images in Microsoft Excel and Microsoft Word.</span></span> <span data-ttu-id="455f4-106">In questo esempio verranno esaminate le configurazioni ER per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="455f4-106">In this example, you will review ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="455f4-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="455f4-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="455f4-108">I passaggi possono essere completati mediante il set di dati USMF.</span><span class="sxs-lookup"><span data-stu-id="455f4-108">The steps can be completed by using the USMF data set.</span></span>


## <a name="review-the-imported-data-model"></a><span data-ttu-id="455f4-109">Esaminare il modello dati importato</span><span class="sxs-lookup"><span data-stu-id="455f4-109">Review the imported data model</span></span>
1. <span data-ttu-id="455f4-110">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="455f4-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="455f4-111">Nella struttura selezionare "Model for cheques".</span><span class="sxs-lookup"><span data-stu-id="455f4-111">In the tree, select 'Model for cheques'.</span></span>
3. <span data-ttu-id="455f4-112">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="455f4-112">Click Designer.</span></span>
    * <span data-ttu-id="455f4-113">Questo modello è progettato per rappresentare gli assegni di pagamento da un punto di vista aziendale e il mapping del modello alle origini dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="455f4-113">This model is designed to represent payment cheques from the business standpoint and the mapping of this model to the application’s data sources.</span></span> <span data-ttu-id="455f4-114">Far esaminare il modello dal progettista delle operazioni ER.</span><span class="sxs-lookup"><span data-stu-id="455f4-114">Review this model by the ER Operations designer.</span></span> <span data-ttu-id="455f4-115">Si notino gli attributi degli elementi del modello presentati, ovvero struttura, nome, descrizione, tipo di dati e così via.</span><span class="sxs-lookup"><span data-stu-id="455f4-115">Note the attributes of the model elements that are presented: structure, name, description, data type, and so on.</span></span>   
4. <span data-ttu-id="455f4-116">Nella struttura espandere "root".</span><span class="sxs-lookup"><span data-stu-id="455f4-116">In the tree, expand 'root'.</span></span>
5. <span data-ttu-id="455f4-117">Nella struttura selezionare "root\cheques".</span><span class="sxs-lookup"><span data-stu-id="455f4-117">In the tree, select 'root\cheques'.</span></span>
6. <span data-ttu-id="455f4-118">Nella struttura espandere "root\cheques".</span><span class="sxs-lookup"><span data-stu-id="455f4-118">In the tree, expand 'root\cheques'.</span></span>
7. <span data-ttu-id="455f4-119">Nella struttura espandere "root\cheques\attributes".</span><span class="sxs-lookup"><span data-stu-id="455f4-119">In the tree, expand 'root\cheques\attributes'.</span></span>
8. <span data-ttu-id="455f4-120">Nella struttura espandere "root\payer".</span><span class="sxs-lookup"><span data-stu-id="455f4-120">In the tree, expand 'root\payer'.</span></span>
9. <span data-ttu-id="455f4-121">Nella struttura selezionare "root\istestrun".</span><span class="sxs-lookup"><span data-stu-id="455f4-121">In the tree, select 'root\istestrun'.</span></span>
10. <span data-ttu-id="455f4-122">Nella struttura selezionare "root\layout".</span><span class="sxs-lookup"><span data-stu-id="455f4-122">In the tree, select 'root\layout'.</span></span>
    * <span data-ttu-id="455f4-123">L'elemento layout del modello rappresenta i dettagli del layout del modulo dell'assegno di stampa per il conto bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="455f4-123">The layout element of this model represents the details of the printing cheque form layout for the selected bank account.</span></span> <span data-ttu-id="455f4-124">Sono inoltre inclusi due nodi del tipo di dati Container per archiviare immagini.</span><span class="sxs-lookup"><span data-stu-id="455f4-124">It also includes two nodes of the Container data type to store images.</span></span>   
11. <span data-ttu-id="455f4-125">Nella struttura espandere "root\layout".</span><span class="sxs-lookup"><span data-stu-id="455f4-125">In the tree, expand 'root\layout'.</span></span>
12. <span data-ttu-id="455f4-126">Nella struttura selezionare "root\layout\company logo".</span><span class="sxs-lookup"><span data-stu-id="455f4-126">In the tree, select 'root\layout\company logo'.</span></span>
13. <span data-ttu-id="455f4-127">Nella struttura espandere "root\layout\company logo".</span><span class="sxs-lookup"><span data-stu-id="455f4-127">In the tree, expand 'root\layout\company logo'.</span></span>
14. <span data-ttu-id="455f4-128">Nella struttura selezionare "root\layout\company logo\image".</span><span class="sxs-lookup"><span data-stu-id="455f4-128">In the tree, select 'root\layout\company logo\image'.</span></span>
15. <span data-ttu-id="455f4-129">Nella struttura selezionare "root\layout\company logo\isprinted".</span><span class="sxs-lookup"><span data-stu-id="455f4-129">In the tree, select 'root\layout\company logo\isprinted'.</span></span>
16. <span data-ttu-id="455f4-130">Nella struttura selezionare "root\layout\signature".</span><span class="sxs-lookup"><span data-stu-id="455f4-130">In the tree, select 'root\layout\signature'.</span></span>
17. <span data-ttu-id="455f4-131">Nella struttura espandere "root\layout\signature".</span><span class="sxs-lookup"><span data-stu-id="455f4-131">In the tree, expand 'root\layout\signature'.</span></span>
18. <span data-ttu-id="455f4-132">Nella struttura selezionare "root\layout\signature\image".</span><span class="sxs-lookup"><span data-stu-id="455f4-132">In the tree, select 'root\layout\signature\image'.</span></span>
19. <span data-ttu-id="455f4-133">Nella struttura selezionare "root\layout\signature\isprinted".</span><span class="sxs-lookup"><span data-stu-id="455f4-133">In the tree, select 'root\layout\signature\isprinted'.</span></span>
    * <span data-ttu-id="455f4-134">Si noti che due elementi del modello dati dell'immagine sono associati ai campi delle tabelle contenenti le immagini del logo della società e la firma della persona autorizzata in formato binario.</span><span class="sxs-lookup"><span data-stu-id="455f4-134">Note that two image data model elements are bound to the fields of the tables that contain images of the company logo and the authorized person’s signature in binary format.</span></span>  
20. <span data-ttu-id="455f4-135">Nella struttura espandere "root\layout\watermark".</span><span class="sxs-lookup"><span data-stu-id="455f4-135">In the tree, expand 'root\layout\watermark'.</span></span>
21. <span data-ttu-id="455f4-136">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="455f4-136">Click Map model to datasource.</span></span>
22. <span data-ttu-id="455f4-137">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="455f4-137">Click Designer.</span></span>
23. <span data-ttu-id="455f4-138">Nella struttura espandere "chequesselected".</span><span class="sxs-lookup"><span data-stu-id="455f4-138">In the tree, expand 'chequesselected'.</span></span>
24. <span data-ttu-id="455f4-139">Nella struttura espandere "layout".</span><span class="sxs-lookup"><span data-stu-id="455f4-139">In the tree, expand 'layout'.</span></span>
25. <span data-ttu-id="455f4-140">Nella struttura espandere "layout\company logo".</span><span class="sxs-lookup"><span data-stu-id="455f4-140">In the tree, expand 'layout\company logo'.</span></span>
26. <span data-ttu-id="455f4-141">Nella struttura espandere "layout\signature".</span><span class="sxs-lookup"><span data-stu-id="455f4-141">In the tree, expand 'layout\signature'.</span></span>
27. <span data-ttu-id="455f4-142">Nella struttura espandere "layout\watermark".</span><span class="sxs-lookup"><span data-stu-id="455f4-142">In the tree, expand 'layout\watermark'.</span></span>
28. <span data-ttu-id="455f4-143">Attivare 'Mostra dettagli'.</span><span class="sxs-lookup"><span data-stu-id="455f4-143">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="455f4-144">Si noti che l'elemento del modello dati degli assegni è associato alla tabella TmpChequePrintout che, in fase di esecuzione, contiene i record per gli assegni che l'utente ha selezionato per la stampa.</span><span class="sxs-lookup"><span data-stu-id="455f4-144">Note that the cheques data model element is bound to the TmpChequePrintout table that, at runtime, will contain records for cheques that the user has selected for printing.</span></span>   
29. <span data-ttu-id="455f4-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="455f4-145">Close the page.</span></span>
30. <span data-ttu-id="455f4-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="455f4-146">Close the page.</span></span>
31. <span data-ttu-id="455f4-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="455f4-147">Close the page.</span></span>

## <a name="review-the-imported-format"></a><span data-ttu-id="455f4-148">Esaminare il formato importato</span><span class="sxs-lookup"><span data-stu-id="455f4-148">Review the imported format</span></span>
1. <span data-ttu-id="455f4-149">Nella struttura espandere "Model for cheques".</span><span class="sxs-lookup"><span data-stu-id="455f4-149">In the tree, expand 'Model for cheques'.</span></span>
2. <span data-ttu-id="455f4-150">Nella struttura selezionare "Model for cheques\Cheques printing format".</span><span class="sxs-lookup"><span data-stu-id="455f4-150">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
3. <span data-ttu-id="455f4-151">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="455f4-151">Click Designer.</span></span>
4. <span data-ttu-id="455f4-152">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="455f4-152">Click Attachments.</span></span>
5. <span data-ttu-id="455f4-153">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="455f4-153">Click Open.</span></span>
    * <span data-ttu-id="455f4-154">Aprire il modello di report allegato in Excel.</span><span class="sxs-lookup"><span data-stu-id="455f4-154">Open the attached report’s template in Excel.</span></span>  
    * <span data-ttu-id="455f4-155">Esaminare il modello di Excel del report allegato che verrà utilizzato per stampare gli assegni.</span><span class="sxs-lookup"><span data-stu-id="455f4-155">Review the attached report’s Excel template that will be used to print cheques.</span></span> <span data-ttu-id="455f4-156">Il modello contiene due assegni per pagina ed è progettato per stampare gli assegni nel modulo prestampato.</span><span class="sxs-lookup"><span data-stu-id="455f4-156">The template contains two cheques per page and is designed to print cheques to the preprinted form.</span></span> <span data-ttu-id="455f4-157">Si noti che sono incorporate due immagini vuote</span><span class="sxs-lookup"><span data-stu-id="455f4-157">Note that two blank images are embedded.</span></span> <span data-ttu-id="455f4-158">per il logo della società e la firma della persona che autorizza un pagamento.</span><span class="sxs-lookup"><span data-stu-id="455f4-158">These blank images are for the company logo and the signature of the person who is authorizing a payment.</span></span> <span data-ttu-id="455f4-159">Verificare che le immagini siano denominate CompLogo e SignatureImage, rispettivamente, in Excel.</span><span class="sxs-lookup"><span data-stu-id="455f4-159">Verify that the images are named CompLogo and SignatureImage, respectively, in Excel.</span></span>   
6. <span data-ttu-id="455f4-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="455f4-160">Close the page.</span></span>
7. <span data-ttu-id="455f4-161">Nella struttura espandere "Report".</span><span class="sxs-lookup"><span data-stu-id="455f4-161">In the tree, expand 'Report'.</span></span>
8. <span data-ttu-id="455f4-162">Nella struttura espandere "Report\ChequeLines".</span><span class="sxs-lookup"><span data-stu-id="455f4-162">In the tree, expand 'Report\ChequeLines'.</span></span>
9. <span data-ttu-id="455f4-163">Nella struttura selezionare "Report\ChequeLines\CompLogo".</span><span class="sxs-lookup"><span data-stu-id="455f4-163">In the tree, select 'Report\ChequeLines\CompLogo'.</span></span>
10. <span data-ttu-id="455f4-164">Attivare 'Mostra dettagli'.</span><span class="sxs-lookup"><span data-stu-id="455f4-164">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="455f4-165">Si noti che l'elemento della cella in formato "CompLogo" rappresenta l'elemento di Excel utilizzato per inserire l'immagine del logo della società nel report.</span><span class="sxs-lookup"><span data-stu-id="455f4-165">Note that the ‘CompLogo’ format’s cell element represents the Excel item that is used to populate the company logo image in the report.</span></span> <span data-ttu-id="455f4-166">Questo elemento di formato è associato all'elemento del modello dati che, in fase di esecuzione, contiene un'immagine del logo della società in formato binario.</span><span class="sxs-lookup"><span data-stu-id="455f4-166">This format element is bound to the image data model element that, at runtime, contains a company logo image in binary format.</span></span>   
11. <span data-ttu-id="455f4-167">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="455f4-167">Click the Mapping tab.</span></span>
12. <span data-ttu-id="455f4-168">Fare clic su Modifica abilitata.</span><span class="sxs-lookup"><span data-stu-id="455f4-168">Click Edit enabled.</span></span>
    * <span data-ttu-id="455f4-169">Si noti che è possibile creare l'elemento della cella del formato "CompLogo" in modo che non sia più abilitato.</span><span class="sxs-lookup"><span data-stu-id="455f4-169">Note that you can make the ‘CompLogo’ format’s cell element so that it’s no longer enabled.</span></span> <span data-ttu-id="455f4-170">In questo caso, l'elemento immagine di Excel associato nasconderà il logo della società nel report generato.</span><span class="sxs-lookup"><span data-stu-id="455f4-170">In this case, the associated Excel image element will hide a company logo in the generated report.</span></span> <span data-ttu-id="455f4-171">Se l'espressione attivata restituisce TRUE e l'associazione definita non è associata ad alcuna immagine, l'elemento immagine di Excel associato visualizzerà un'immagine che è stata salvata nel modello Excel.</span><span class="sxs-lookup"><span data-stu-id="455f4-171">If the enabled expression returns TRUE and the defined binding brings no image, the associated Excel image element will show an image that has been saved in the Excel template.</span></span>   
13. <span data-ttu-id="455f4-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="455f4-172">Close the page.</span></span>
14. <span data-ttu-id="455f4-173">Nella struttura espandere "labels: Container".</span><span class="sxs-lookup"><span data-stu-id="455f4-173">In the tree, expand 'labels: Container'.</span></span>
    * <span data-ttu-id="455f4-174">Alcune etichette presentate nel modulo dell'assegno prestampato verranno incluse nel report quando è creato a scopo di verifica.</span><span class="sxs-lookup"><span data-stu-id="455f4-174">Some labels that are presented in the preprinted cheque form will be included in the report when it’s created for testing purposes.</span></span> <span data-ttu-id="455f4-175">Tuttavia, le etichette non verranno stampate durante la stampa effettiva in quanto il modulo prestampato le include già.</span><span class="sxs-lookup"><span data-stu-id="455f4-175">However, those labels won’t be printed during real printing, because the preprinted form already includes them.</span></span>  
15. <span data-ttu-id="455f4-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="455f4-176">Close the page.</span></span>


