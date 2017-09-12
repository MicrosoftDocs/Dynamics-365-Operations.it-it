--- 
title: Modificare ed eseguire il formato per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 58e79f4d969e8bf0c7f150fd307f9f48334d6405
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="modify-and-run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="bc549-103">Modificare ed eseguire il formato per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="bc549-103">Modify and run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc549-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="bc549-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="bc549-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="bc549-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="bc549-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 4: eseguire il formato)'.</span><span class="sxs-lookup"><span data-stu-id="bc549-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4): Run format” procedure.</span></span>

<span data-ttu-id="bc549-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="bc549-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="bc549-108">Modificare il formato per popolare gli allegati nella generazione di messaggi in formato binario</span><span class="sxs-lookup"><span data-stu-id="bc549-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="bc549-109">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="bc549-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="bc549-110">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="bc549-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="bc549-111">Nella struttura espandere 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="bc549-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="bc549-112">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)\Messaggio di esempio fattura elettronica'.</span><span class="sxs-lookup"><span data-stu-id="bc549-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="bc549-113">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="bc549-113">Click Designer.</span></span>
    * <span data-ttu-id="bc549-114">Popolerete il messaggio della fattura nell'output di generazione come file XML tramite codifica UNICODE.</span><span class="sxs-lookup"><span data-stu-id="bc549-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="bc549-115">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="bc549-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="bc549-116">Nella struttura selezionare "Comune\File".</span><span class="sxs-lookup"><span data-stu-id="bc549-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="bc549-117">Nel campo Nome digitare 'Messaggio Xml'.</span><span class="sxs-lookup"><span data-stu-id="bc549-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="bc549-118">Messaggio Xml</span><span class="sxs-lookup"><span data-stu-id="bc549-118">Xml message</span></span>  
9. <span data-ttu-id="bc549-119">Nel campo Codifica digitare "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="bc549-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="bc549-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="bc549-120">UTF-8</span></span>  
10. <span data-ttu-id="bc549-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bc549-121">Click OK.</span></span>
    * <span data-ttu-id="bc549-122">Configurare l'output di generazione come file compresso.</span><span class="sxs-lookup"><span data-stu-id="bc549-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="bc549-123">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="bc549-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="bc549-124">Nella struttura selezionare 'Comune\Cartella'.</span><span class="sxs-lookup"><span data-stu-id="bc549-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="bc549-125">Nel campo Nome digitare 'Output ZIP'.</span><span class="sxs-lookup"><span data-stu-id="bc549-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="bc549-126">Output ZIP</span><span class="sxs-lookup"><span data-stu-id="bc549-126">Zip output</span></span>  
14. <span data-ttu-id="bc549-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bc549-127">Click OK.</span></span>
15. <span data-ttu-id="bc549-128">Nella struttura selezionare 'Output ZIP'.</span><span class="sxs-lookup"><span data-stu-id="bc549-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="bc549-129">Aggiungere allegati al file compresso di generazione come file con i nomi e le estensioni originali.</span><span class="sxs-lookup"><span data-stu-id="bc549-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="bc549-130">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="bc549-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="bc549-131">Nella struttura selezionare "Comune\File".</span><span class="sxs-lookup"><span data-stu-id="bc549-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="bc549-132">Digitare 'File allegato' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="bc549-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="bc549-133">File allegato</span><span class="sxs-lookup"><span data-stu-id="bc549-133">Attached file</span></span>  
19. <span data-ttu-id="bc549-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bc549-134">Click OK.</span></span>
20. <span data-ttu-id="bc549-135">Nella struttura selezionare 'Output ZIP\File allegato'.</span><span class="sxs-lookup"><span data-stu-id="bc549-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="bc549-136">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="bc549-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="bc549-137">Nella struttura selezionare  'Testo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="bc549-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="bc549-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bc549-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="bc549-139">Mappare gli elementi del nuovo formato al modello dati</span><span class="sxs-lookup"><span data-stu-id="bc549-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="bc549-140">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="bc549-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="bc549-141">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="bc549-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="bc549-142">Nella struttura espandere 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="bc549-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="bc549-143">Nella struttura selezionare 'Output ZIP\File allegato\Base64'.</span><span class="sxs-lookup"><span data-stu-id="bc549-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="bc549-144">Nella struttura selezionare 'modello\Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="bc549-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="bc549-145">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="bc549-145">Click Bind.</span></span>
7. <span data-ttu-id="bc549-146">Nella struttura selezionare 'Output ZIP\File allegato'.</span><span class="sxs-lookup"><span data-stu-id="bc549-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="bc549-147">Fare clic su Modifica nome del file.</span><span class="sxs-lookup"><span data-stu-id="bc549-147">Click Edit filename.</span></span>
9. <span data-ttu-id="bc549-148">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="bc549-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="bc549-149">Nella struttura espandere 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="bc549-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="bc549-150">Nella struttura selezionare 'modello\Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="bc549-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="bc549-151">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="bc549-151">Click Add data source.</span></span>
13. <span data-ttu-id="bc549-152">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="bc549-152">Click Save.</span></span>
14. <span data-ttu-id="bc549-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bc549-153">Close the page.</span></span>
15. <span data-ttu-id="bc549-154">Nella struttura selezionare 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="bc549-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="bc549-155">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="bc549-155">Click Bind.</span></span>
17. <span data-ttu-id="bc549-156">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="bc549-156">Click Save.</span></span>
18. <span data-ttu-id="bc549-157">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bc549-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="bc549-158">Eseguire il report progettato per la fattura selezionata</span><span class="sxs-lookup"><span data-stu-id="bc549-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="bc549-159">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="bc549-159">Click Run.</span></span>
2. <span data-ttu-id="bc549-160">Espandere la sezione Record da includere ().</span><span class="sxs-lookup"><span data-stu-id="bc549-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="bc549-161">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="bc549-161">Click Filter.</span></span>
4. <span data-ttu-id="bc549-162">Selezionare la riga del giornale di registrazione fatture cliente e il campo Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="bc549-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="bc549-163">Nel campo Criterim nel campo "Ordine cliente" di criteri, digitare il numero di ordine 000148.</span><span class="sxs-lookup"><span data-stu-id="bc549-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="bc549-164">000148</span><span class="sxs-lookup"><span data-stu-id="bc549-164">000148</span></span>  
6. <span data-ttu-id="bc549-165">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bc549-165">Click OK.</span></span>
7. <span data-ttu-id="bc549-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bc549-166">Click OK.</span></span>
    * <span data-ttu-id="bc549-167">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="bc549-167">Review the generated output.</span></span> <span data-ttu-id="bc549-168">Si noti che, oltre al messaggio della fattura in formato XML, un singolo file è stato creato per ciascun allegato.</span><span class="sxs-lookup"><span data-stu-id="bc549-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="bc549-169">I file degli allegati vengono popolati con l'output compresso in formato binario.</span><span class="sxs-lookup"><span data-stu-id="bc549-169">The attachment files are populated with the zipped output in binary format.</span></span>  

