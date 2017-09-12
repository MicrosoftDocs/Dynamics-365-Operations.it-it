--- 
title: Generare i report nei formati Microsoft Office con immagini incorporate per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore di report elettronici può progettare configurazioni ER per generare documenti elettronici in formato MS Office (Excel e Word) contenenti immagini incorporate."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: de2840ebc6c91e313546859f5c0d8939eb80977b
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="generate-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er"></a><span data-ttu-id="996c0-103">Generare i report nei formati Microsoft Office con immagini incorporate per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="996c0-103">Generate reports in Microsoft Office formats with embedded images for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="996c0-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore di report elettronici può progettare configurazioni ER per generare documenti elettronici in formato MS Office (Excel e Word) contenenti immagini incorporate.</span><span class="sxs-lookup"><span data-stu-id="996c0-104">The following steps explain how a user playing either ‘System administrator’ or ‘Electronic reporting developer’ role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="996c0-105">In questo esempio verranno create configurazioni ER per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="996c0-105">In this example, you will use created ER configurations for sample company, ‘Litware, Inc.’.</span></span>  <span data-ttu-id="996c0-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività "ER Creare report in formati di Microsoft Office con immagini incluse (Parte 2: Esaminare le configurazioni)".</span><span class="sxs-lookup"><span data-stu-id="996c0-106">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)” task guide.</span></span> <span data-ttu-id="996c0-107">Queste operazioni possono essere eseguite nella società "USMF".</span><span class="sxs-lookup"><span data-stu-id="996c0-107">These steps can be performed in ‘USMF’ company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="996c0-108">Eseguire il formato con il mapping di modello iniziale</span><span class="sxs-lookup"><span data-stu-id="996c0-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="996c0-109">Andare a Gestione cassa e banche > Conti bancari > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="996c0-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="996c0-110">Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="996c0-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="996c0-111">Nel riquadro azioni, fare clic su Imposta.</span><span class="sxs-lookup"><span data-stu-id="996c0-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="996c0-112">Fare clic su Verifica.</span><span class="sxs-lookup"><span data-stu-id="996c0-112">Click Check.</span></span>
5. <span data-ttu-id="996c0-113">Fare clic su Stampa di prova.</span><span class="sxs-lookup"><span data-stu-id="996c0-113">Click Print test.</span></span>
    * <span data-ttu-id="996c0-114">Eseguire il formato a scopo di verifica.</span><span class="sxs-lookup"><span data-stu-id="996c0-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="996c0-115">Selezionare Sì nel campo Formato assegno negoziabile.</span><span class="sxs-lookup"><span data-stu-id="996c0-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="996c0-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="996c0-116">Click OK.</span></span>
    * <span data-ttu-id="996c0-117">Esaminare l'output creato.</span><span class="sxs-lookup"><span data-stu-id="996c0-117">Review the created output.</span></span> <span data-ttu-id="996c0-118">Si noti che il logo della società viene visualizzato nel report così come la firma della persona autorizzata.</span><span class="sxs-lookup"><span data-stu-id="996c0-118">Note that the company logo is presented in the report as well as the authorized person’s signature.</span></span> <span data-ttu-id="996c0-119">L'immagine della firma viene ricavata dal tipo di dati "Container" del record del layout dell'assegno associato al conto bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="996c0-119">The signature image is taken from the field of the ‘Container’ data type of the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="996c0-120">Espandere la sezione Copie.</span><span class="sxs-lookup"><span data-stu-id="996c0-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="996c0-121">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="996c0-121">Click Edit.</span></span>
10. <span data-ttu-id="996c0-122">Nel campo Filigrana, immettere "Stampa filigrana come Annulla".</span><span class="sxs-lookup"><span data-stu-id="996c0-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="996c0-123">Modificare l'impostazione del layout della filigrana per visualizzare il testo della filigrana nella generazione di documenti in un elemento forma di Excel.</span><span class="sxs-lookup"><span data-stu-id="996c0-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="996c0-124">Fare clic su Stampa di prova.</span><span class="sxs-lookup"><span data-stu-id="996c0-124">Click Print test.</span></span>
12. <span data-ttu-id="996c0-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="996c0-125">Click OK.</span></span>
    * <span data-ttu-id="996c0-126">Esaminare l'output creato.</span><span class="sxs-lookup"><span data-stu-id="996c0-126">Review the created output.</span></span> <span data-ttu-id="996c0-127">Si noti che la filigrana viene visualizzata nel report creato in base all'opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="996c0-127">Note that the watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="996c0-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-128">Close the page.</span></span>
14. <span data-ttu-id="996c0-129">Nel riquadro azioni, fare clic su Gestisci pagamenti.</span><span class="sxs-lookup"><span data-stu-id="996c0-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="996c0-130">Fare clic su Assegni.</span><span class="sxs-lookup"><span data-stu-id="996c0-130">Click Checks.</span></span>
16. <span data-ttu-id="996c0-131">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="996c0-131">Click Show filters.</span></span>
17. <span data-ttu-id="996c0-132">Applicare i filtri seguenti, immettendo un valore di filtro pari a "381","385","389" nel campo del numero di assegno utilizzando l'operatore "è uno di".</span><span class="sxs-lookup"><span data-stu-id="996c0-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="996c0-133">Nell'elenco selezionare tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="996c0-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="996c0-134">Fare clic su Stampa copia assegno.</span><span class="sxs-lookup"><span data-stu-id="996c0-134">Click Print check copy.</span></span>
    * <span data-ttu-id="996c0-135">Eseguire il formato per ristampare gli assegni selezionati.</span><span class="sxs-lookup"><span data-stu-id="996c0-135">Run the format to re-print the selected cheques.</span></span>  
    * <span data-ttu-id="996c0-136">Esaminare l'output creato.</span><span class="sxs-lookup"><span data-stu-id="996c0-136">Review the created output.</span></span> <span data-ttu-id="996c0-137">Si noti che gli assegni selezionati sono stati ristampati.</span><span class="sxs-lookup"><span data-stu-id="996c0-137">Note that the selected cheques have been re-printed.</span></span> <span data-ttu-id="996c0-138">Il logo e le etichette delle società non verranno stampati perché sono visualizzati nel modulo prestampato.</span><span class="sxs-lookup"><span data-stu-id="996c0-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="996c0-139">Modificare il mapping del modello dati importato</span><span class="sxs-lookup"><span data-stu-id="996c0-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="996c0-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-140">Close the page.</span></span>
2. <span data-ttu-id="996c0-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-141">Close the page.</span></span>
3. <span data-ttu-id="996c0-142">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="996c0-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="996c0-143">Nella struttura selezionare "Model for cheques".</span><span class="sxs-lookup"><span data-stu-id="996c0-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="996c0-144">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="996c0-144">Click Designer.</span></span>
6. <span data-ttu-id="996c0-145">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="996c0-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="996c0-146">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="996c0-146">Click Designer.</span></span>
    * <span data-ttu-id="996c0-147">Cambieremo l'associazione dell'elemento di firma del modello dati per ottenere l'immagine della firma del file che è stato collegato al record del layout di assegno associato al conto bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="996c0-147">We will change the binding of the data model’s signature item to get the signature image from the file that has been attached to the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="996c0-148">Disattivare la visualizzazione dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="996c0-148">Turn Show details off.</span></span>
9. <span data-ttu-id="996c0-149">Nella struttura espandere "layout".</span><span class="sxs-lookup"><span data-stu-id="996c0-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="996c0-150">Nella struttura espandere "layout\signature".</span><span class="sxs-lookup"><span data-stu-id="996c0-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="996c0-151">Nella struttura selezionare "layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp".</span><span class="sxs-lookup"><span data-stu-id="996c0-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="996c0-152">Nella struttura espandere "chequesaccount".</span><span class="sxs-lookup"><span data-stu-id="996c0-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="996c0-153">Nella struttura espandere "chequesaccount\<Relations".</span><span class="sxs-lookup"><span data-stu-id="996c0-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="996c0-154">Nella struttura espandere "chequesaccount\<Relations\BankChequeLayout".</span><span class="sxs-lookup"><span data-stu-id="996c0-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="996c0-155">Nella struttura espandere "chequesaccount\<Relations\BankChequeLayout\<Relations".</span><span class="sxs-lookup"><span data-stu-id="996c0-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="996c0-156">Nella struttura espandere "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents".</span><span class="sxs-lookup"><span data-stu-id="996c0-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="996c0-157">Nella struttura selezionare "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()".</span><span class="sxs-lookup"><span data-stu-id="996c0-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="996c0-158">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="996c0-158">Click Bind.</span></span>
19. <span data-ttu-id="996c0-159">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="996c0-159">Click Save.</span></span>
20. <span data-ttu-id="996c0-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-160">Close the page.</span></span>
21. <span data-ttu-id="996c0-161">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-161">Close the page.</span></span>
22. <span data-ttu-id="996c0-162">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-162">Close the page.</span></span>
23. <span data-ttu-id="996c0-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="996c0-164">Eseguire il formato utilizzando il mapping del modello modificato</span><span class="sxs-lookup"><span data-stu-id="996c0-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="996c0-165">Andare a Gestione cassa e banche > Conti bancari > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="996c0-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="996c0-166">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="996c0-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="996c0-167">Ad esempio, filtrare nel campo Conto bancario in base a un valore "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="996c0-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="996c0-168">Nel riquadro azioni, fare clic su Imposta.</span><span class="sxs-lookup"><span data-stu-id="996c0-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="996c0-169">Fare clic su Verifica.</span><span class="sxs-lookup"><span data-stu-id="996c0-169">Click Check.</span></span>
5. <span data-ttu-id="996c0-170">Fare clic su Stampa di prova.</span><span class="sxs-lookup"><span data-stu-id="996c0-170">Click Print test.</span></span>
6. <span data-ttu-id="996c0-171">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="996c0-171">Click OK.</span></span>
    * <span data-ttu-id="996c0-172">Esaminare l'output creato.</span><span class="sxs-lookup"><span data-stu-id="996c0-172">Review the created output.</span></span> <span data-ttu-id="996c0-173">Si noti che l'immagine dall'allegato di gestione documenti viene inviata come firma di una persona autorizzata.</span><span class="sxs-lookup"><span data-stu-id="996c0-173">Note that the image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="996c0-174">Utilizzare il documento di Microsoft Word come modello nel formato importato</span><span class="sxs-lookup"><span data-stu-id="996c0-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="996c0-175">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-175">Close the page.</span></span>
2. <span data-ttu-id="996c0-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-176">Close the page.</span></span>
3. <span data-ttu-id="996c0-177">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="996c0-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="996c0-178">Nella struttura espandere "Model for cheques".</span><span class="sxs-lookup"><span data-stu-id="996c0-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="996c0-179">Nella struttura selezionare "Model for cheques\Cheques printing format".</span><span class="sxs-lookup"><span data-stu-id="996c0-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="996c0-180">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="996c0-180">Click Designer.</span></span>
7. <span data-ttu-id="996c0-181">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="996c0-181">Click Attachments.</span></span>
8. <span data-ttu-id="996c0-182">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="996c0-182">Click Delete.</span></span>
9. <span data-ttu-id="996c0-183">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="996c0-183">Click Yes.</span></span>
10. <span data-ttu-id="996c0-184">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="996c0-184">Click New.</span></span>
11. <span data-ttu-id="996c0-185">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="996c0-185">Click File.</span></span>
    * <span data-ttu-id="996c0-186">Fare clic su Sfoglia e selezionare il file modello di assegno in formato Word scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="996c0-186">Click Browse and select the downloaded in advance ‘Cheque template Word.docx’ file.</span></span>  
12. <span data-ttu-id="996c0-187">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-187">Close the page.</span></span>
13. <span data-ttu-id="996c0-188">Nel campo Modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="996c0-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="996c0-189">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="996c0-189">Click Save.</span></span>
15. <span data-ttu-id="996c0-190">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-190">Close the page.</span></span>
16. <span data-ttu-id="996c0-191">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="996c0-191">Click Edit.</span></span>
17. <span data-ttu-id="996c0-192">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="996c0-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="996c0-193">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="996c0-193">Close the page.</span></span>
19. <span data-ttu-id="996c0-194">Andare a Gestione cassa e banche > Conti bancari > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="996c0-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="996c0-195">Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="996c0-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="996c0-196">Fare clic su Verifica.</span><span class="sxs-lookup"><span data-stu-id="996c0-196">Click Check.</span></span>
22. <span data-ttu-id="996c0-197">Fare clic su Stampa di prova.</span><span class="sxs-lookup"><span data-stu-id="996c0-197">Click Print test.</span></span>
23. <span data-ttu-id="996c0-198">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="996c0-198">Click OK.</span></span>
    * <span data-ttu-id="996c0-199">Esaminare l'output creato.</span><span class="sxs-lookup"><span data-stu-id="996c0-199">Review the created output.</span></span> <span data-ttu-id="996c0-200">Si noti che l'output è stato generato come documento di Microsoft Word con immagini incorporate che presentano il logo della società, la firma di una persona autorizzata e il testo selezionato della filigrana.</span><span class="sxs-lookup"><span data-stu-id="996c0-200">Note that the output has been generated as a MS Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  


