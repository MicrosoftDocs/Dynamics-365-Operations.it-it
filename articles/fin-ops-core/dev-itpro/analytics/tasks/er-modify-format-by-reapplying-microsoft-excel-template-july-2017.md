---
title: Modificare i formati riapplicando i modelli di Excel
description: Per completare i passaggi in questa procedura, è innanzitutto necessario completare la procedura "ER - Progettare una configurazione per la creazione di report nel formato OPENXML".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ca6707095765c25851ee864a99844a82844fae1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564316"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a><span data-ttu-id="e0036-103">Modificare i formati riapplicando i modelli di Excel</span><span class="sxs-lookup"><span data-stu-id="e0036-103">Modify formats by reapplying Excel templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0036-104">Per completare i passaggi in questa procedura, è innanzitutto necessario completare la procedura "ER - Progettare una configurazione per la creazione di report nel formato OPENXML".</span><span class="sxs-lookup"><span data-stu-id="e0036-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="e0036-105">In questa procedura viene illustrato come modificare la configurazione ER riapplicando un modello di Microsoft Excel modificato.</span><span class="sxs-lookup"><span data-stu-id="e0036-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="e0036-106">In questa procedura verrà importato un modello Excel modificato nelle configurazioni in formato ER create per la società di esempio, Litware, Inc. e verranno generati i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="e0036-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="e0036-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="e0036-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="e0036-108">Tali passaggi possono essere completati mediante il set di dati GBSI.</span><span class="sxs-lookup"><span data-stu-id="e0036-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="e0036-109">Prima di iniziare, scaricare e salvare il file, SampleVendPaymWsReport2.xlsx elencato nell'argomento della Guida "Modificare un formato per la creazione di report elettronici riapplicando un modello di Microsoft Excel" (modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="e0036-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="e0036-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="e0036-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="e0036-111">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="e0036-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="e0036-112">Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="e0036-112">If you don't see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="e0036-113">Selezionare il formato ER.</span><span class="sxs-lookup"><span data-stu-id="e0036-113">Select the ER format</span></span>
1. <span data-ttu-id="e0036-114">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="e0036-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="e0036-115">Nella struttura espandere "Modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="e0036-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="e0036-116">Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="e0036-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="e0036-117">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="e0036-117">Click Attachments.</span></span>
    * <span data-ttu-id="e0036-118">Si noti che il file Excel SampleVendPaymWsReport.xlsx è attualmente utilizzato come modello per l'elaborazione del giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="e0036-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="e0036-119">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="e0036-119">Click Open.</span></span>
    * <span data-ttu-id="e0036-120">Fare clic su Apri per visualizzare il layout del modello Excel.</span><span class="sxs-lookup"><span data-stu-id="e0036-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="e0036-121">Esaminare il modello.</span><span class="sxs-lookup"><span data-stu-id="e0036-121">Review the template.</span></span> <span data-ttu-id="e0036-122">Si noti che il modello include attualmente i dettagli relativi a ogni riga di pagamento, ovvero numero di conto del fornitore, nome del fornitore, banca, numero di registrazione, numero di conto, importi Dare e Avere e valuta.</span><span class="sxs-lookup"><span data-stu-id="e0036-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="e0036-123">Per questo esempio, verrà esteso l'elenco aggiungendo i dettagli relativi alla data di pagamento.</span><span class="sxs-lookup"><span data-stu-id="e0036-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="e0036-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e0036-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="e0036-125">Riapplicare un nuovo modello Excel al formato ER</span><span class="sxs-lookup"><span data-stu-id="e0036-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="e0036-126">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="e0036-126">Click Designer.</span></span>
    * <span data-ttu-id="e0036-127">Aprire la versione bozza del formato ER selezionato da modificare.</span><span class="sxs-lookup"><span data-stu-id="e0036-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="e0036-128">Nel Riquadro azioni fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="e0036-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="e0036-129">Fare clic su Aggiornamento da Excel.</span><span class="sxs-lookup"><span data-stu-id="e0036-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="e0036-130">Fare clic su "Aggiorna modello", quindi selezionare il file SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="e0036-130">Click 'Update template', and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="e0036-131">Fare clic su Aggiorna modello e cercare il file SampleVendPaymWsReport2.xlsx scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e0036-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="e0036-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0036-132">Click OK.</span></span>
    * <span data-ttu-id="e0036-133">Il modello SampleVendPaymWsReport2.xlsx viene applicato.</span><span class="sxs-lookup"><span data-stu-id="e0036-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="e0036-134">La struttura del formato ER verrà sincronizzata con il contenuto del modello, i cui elementi vengono aggiunti al formato ER.</span><span class="sxs-lookup"><span data-stu-id="e0036-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="e0036-135">Tutti gli elementi presenti nel formato ER non inclusi nel modello verranno rimossi dalla definizione di formato.</span><span class="sxs-lookup"><span data-stu-id="e0036-135">Any existing elements in the ER format that aren't included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="e0036-136">Nella struttura selezionare "Excel".</span><span class="sxs-lookup"><span data-stu-id="e0036-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="e0036-137">Si noti che il campo Modello ora contiene un riferimento al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="e0036-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="e0036-138">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="e0036-138">Click Attachments.</span></span>
7. <span data-ttu-id="e0036-139">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="e0036-139">Click Open.</span></span>
    * <span data-ttu-id="e0036-140">Fare clic su Apri per visualizzare il layout del modello Excel modificato.</span><span class="sxs-lookup"><span data-stu-id="e0036-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="e0036-141">Esaminare il modello.</span><span class="sxs-lookup"><span data-stu-id="e0036-141">Review the template.</span></span> <span data-ttu-id="e0036-142">Si noti che ora è presente una riga per la data di pagamento.</span><span class="sxs-lookup"><span data-stu-id="e0036-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="e0036-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e0036-143">Close the page.</span></span>
9. <span data-ttu-id="e0036-144">Nella struttura espandere "Excel".</span><span class="sxs-lookup"><span data-stu-id="e0036-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="e0036-145">Nella struttura espandere 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="e0036-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="e0036-146">Nella struttura, selezionare "Excel\PaymLines\PaymDate".</span><span class="sxs-lookup"><span data-stu-id="e0036-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="e0036-147">Si noti che il formato ER ora contiene un nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="e0036-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="e0036-148">Una cella, PaymDate, è stata aggiunta al modello Excel.</span><span class="sxs-lookup"><span data-stu-id="e0036-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="e0036-149">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="e0036-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="e0036-150">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="e0036-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="e0036-151">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="e0036-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="e0036-152">Nella struttura selezionare "modello\Pagamenti\Data della transazione(TransactionDate)".</span><span class="sxs-lookup"><span data-stu-id="e0036-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="e0036-153">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="e0036-153">Click Bind.</span></span>
    * <span data-ttu-id="e0036-154">Specificare i dati da aggiungere alla nuova cella in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e0036-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="e0036-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e0036-155">Click Save.</span></span>
18. <span data-ttu-id="e0036-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e0036-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="e0036-157">Attivare la versione bozza modificata del formato ER da utilizzare per l'elaborazione del giornale di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="e0036-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="e0036-158">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="e0036-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="e0036-159">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="e0036-159">Click User parameters.</span></span>
3. <span data-ttu-id="e0036-160">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e0036-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="e0036-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0036-161">Click OK.</span></span>
5. <span data-ttu-id="e0036-162">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="e0036-162">Click Edit.</span></span>
6. <span data-ttu-id="e0036-163">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="e0036-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="e0036-164">Utilizzare la versione bozza modificata del formato ER per l'elaborazione del giornale di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="e0036-164">Use the modified draft version of the ER format for payment journal processing</span></span>

<span data-ttu-id="e0036-165">Esaminare il foglio di lavoro creato che include il nuovo dettaglio delle righe di pagamento, ovvero la data di pagamento.</span><span class="sxs-lookup"><span data-stu-id="e0036-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]