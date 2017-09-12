--- 
title: Modificare un formato riapplicando un modello di Microsoft Excel per la creazione di report elettronici (ER)
description: "Per completare i passaggi in questa procedura, è innanzitutto necessario completare la procedura \"ER - Progettare una configurazione per la creazione di report nel formato OPENXML\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: ae1de653354d891e99fb41fa4b10e6910f458cf4
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="modify-a-format-by-reapplying-a-microsoft-excel-template-for-electronic-reporting-er"></a><span data-ttu-id="6a398-103">Modificare un formato riapplicando un modello di Microsoft Excel per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="6a398-103">Modify a format by reapplying a Microsoft Excel template for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a398-104">Per completare i passaggi in questa procedura, è innanzitutto necessario completare la procedura "ER - Progettare una configurazione per la creazione di report nel formato OPENXML".</span><span class="sxs-lookup"><span data-stu-id="6a398-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="6a398-105">In questa procedura viene illustrato come modificare la configurazione ER riapplicando un modello di Microsoft Excel modificato.</span><span class="sxs-lookup"><span data-stu-id="6a398-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="6a398-106">In questa procedura verrà importato un modello Excel modificato nelle configurazioni in formato ER create per la società di esempio, Litware, Inc. e verranno generati i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="6a398-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="6a398-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6a398-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="6a398-108">Tali passaggi possono essere completati mediante il set di dati GBSI.</span><span class="sxs-lookup"><span data-stu-id="6a398-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="6a398-109">Prima di iniziare, scaricare e salvare il file, SampleVendPaymWsReport2.xlsx elencato nell'argomento della Guida "Modificare un formato per la creazione di report elettronici riapplicando un modello di Microsoft Excel" (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="6a398-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="6a398-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6a398-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="6a398-111">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="6a398-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="6a398-112">Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="6a398-112">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="6a398-113">Selezionare il formato ER.</span><span class="sxs-lookup"><span data-stu-id="6a398-113">Select the ER format</span></span>
1. <span data-ttu-id="6a398-114">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="6a398-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="6a398-115">Nella struttura espandere "Modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="6a398-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="6a398-116">Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="6a398-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="6a398-117">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="6a398-117">Click Attachments.</span></span>
    * <span data-ttu-id="6a398-118">Si noti che il file Excel SampleVendPaymWsReport.xlsx è attualmente utilizzato come modello per l'elaborazione del giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="6a398-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="6a398-119">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="6a398-119">Click Open.</span></span>
    * <span data-ttu-id="6a398-120">Fare clic su Apri per visualizzare il layout del modello Excel.</span><span class="sxs-lookup"><span data-stu-id="6a398-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="6a398-121">Esaminare il modello.</span><span class="sxs-lookup"><span data-stu-id="6a398-121">Review the template.</span></span> <span data-ttu-id="6a398-122">Si noti che il modello include attualmente i dettagli relativi a ogni riga di pagamento, ovvero numero di conto del fornitore, nome del fornitore, banca, numero di registrazione, numero di conto, importi Dare e Avere e valuta.</span><span class="sxs-lookup"><span data-stu-id="6a398-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="6a398-123">Per questo esempio, verrà esteso l'elenco aggiungendo i dettagli relativi alla data di pagamento.</span><span class="sxs-lookup"><span data-stu-id="6a398-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="6a398-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6a398-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="6a398-125">Riapplicare un nuovo modello Excel al formato ER</span><span class="sxs-lookup"><span data-stu-id="6a398-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="6a398-126">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="6a398-126">Click Designer.</span></span>
    * <span data-ttu-id="6a398-127">Aprire la versione bozza del formato ER selezionato da modificare.</span><span class="sxs-lookup"><span data-stu-id="6a398-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="6a398-128">Nel Riquadro azioni fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="6a398-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="6a398-129">Fare clic su Aggiornamento da Excel.</span><span class="sxs-lookup"><span data-stu-id="6a398-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="6a398-130">Fare clic su "Aggiorna modello", quindi selezionare il file SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="6a398-130">Click ‘Update template’, and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="6a398-131">Fare clic su Aggiorna modello e cercare il file SampleVendPaymWsReport2.xlsx scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6a398-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="6a398-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6a398-132">Click OK.</span></span>
    * <span data-ttu-id="6a398-133">Il modello SampleVendPaymWsReport2.xlsx viene applicato.</span><span class="sxs-lookup"><span data-stu-id="6a398-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="6a398-134">La struttura del formato ER verrà sincronizzata con il contenuto del modello, i cui elementi vengono aggiunti al formato ER.</span><span class="sxs-lookup"><span data-stu-id="6a398-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="6a398-135">Tutti gli elementi presenti nel formato ER non inclusi nel modello verranno rimossi dalla definizione di formato.</span><span class="sxs-lookup"><span data-stu-id="6a398-135">Any existing elements in the ER format that aren’t included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="6a398-136">Nella struttura selezionare "Excel".</span><span class="sxs-lookup"><span data-stu-id="6a398-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="6a398-137">Si noti che il campo Modello ora contiene un riferimento al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="6a398-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="6a398-138">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="6a398-138">Click Attachments.</span></span>
7. <span data-ttu-id="6a398-139">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="6a398-139">Click Open.</span></span>
    * <span data-ttu-id="6a398-140">Fare clic su Apri per visualizzare il layout del modello Excel modificato.</span><span class="sxs-lookup"><span data-stu-id="6a398-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="6a398-141">Esaminare il modello.</span><span class="sxs-lookup"><span data-stu-id="6a398-141">Review the template.</span></span> <span data-ttu-id="6a398-142">Si noti che ora è presente una riga per la data di pagamento.</span><span class="sxs-lookup"><span data-stu-id="6a398-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="6a398-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6a398-143">Close the page.</span></span>
9. <span data-ttu-id="6a398-144">Nella struttura espandere "Excel".</span><span class="sxs-lookup"><span data-stu-id="6a398-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="6a398-145">Nella struttura espandere 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="6a398-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="6a398-146">Nella struttura, selezionare "Excel\PaymLines\PaymDate".</span><span class="sxs-lookup"><span data-stu-id="6a398-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="6a398-147">Si noti che il formato ER ora contiene un nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="6a398-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="6a398-148">Una cella, PaymDate, è stata aggiunta al modello Excel.</span><span class="sxs-lookup"><span data-stu-id="6a398-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="6a398-149">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="6a398-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="6a398-150">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="6a398-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="6a398-151">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="6a398-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="6a398-152">Nella struttura selezionare "modello\Pagamenti\Data della transazione(TransactionDate)".</span><span class="sxs-lookup"><span data-stu-id="6a398-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="6a398-153">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6a398-153">Click Bind.</span></span>
    * <span data-ttu-id="6a398-154">Specificare i dati da aggiungere alla nuova cella in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6a398-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="6a398-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6a398-155">Click Save.</span></span>
18. <span data-ttu-id="6a398-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6a398-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="6a398-157">Attivare la versione bozza modificata del formato ER da utilizzare per l'elaborazione del giornale di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="6a398-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="6a398-158">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="6a398-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="6a398-159">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="6a398-159">Click User parameters.</span></span>
3. <span data-ttu-id="6a398-160">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6a398-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="6a398-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6a398-161">Click OK.</span></span>
5. <span data-ttu-id="6a398-162">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="6a398-162">Click Edit.</span></span>
6. <span data-ttu-id="6a398-163">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="6a398-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="6a398-164">Utilizzare la versione bozza modificata del formato ER per l'elaborazione del giornale di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="6a398-164">Use the modified draft version of the ER format for payment journal processing</span></span>
    * <span data-ttu-id="6a398-165">Esaminare il foglio di lavoro creato che include il nuovo dettaglio delle righe di pagamento, ovvero la data di pagamento.</span><span class="sxs-lookup"><span data-stu-id="6a398-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  

