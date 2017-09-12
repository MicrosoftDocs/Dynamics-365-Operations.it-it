---
title: Risoluzione dei problemi di importazione di file di rendiconto bancario
description: "È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 51cd32217b2f753f606e3060b4872a8274f16549
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="4188b-107">Risoluzione dei problemi di importazione di file di rendiconto bancario</span><span class="sxs-lookup"><span data-stu-id="4188b-107">Bank statement file import troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4188b-108">È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4188b-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 for Finance and Operations, Enterprise edition supports.</span></span> <span data-ttu-id="4188b-109">A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="4188b-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="4188b-110">Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="4188b-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="4188b-111">In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="4188b-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="4188b-112">In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="4188b-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="4188b-113">Qual è l'errore?</span><span class="sxs-lookup"><span data-stu-id="4188b-113">What is the error?</span></span>
------------------

<span data-ttu-id="4188b-114">Dopo aver tentato di importare un file di rendiconto bancario, passare allo storici processi della gestione dati e ai dettagli di esecuzione per individuare l'errore.</span><span class="sxs-lookup"><span data-stu-id="4188b-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="4188b-115">L'errore potrà aiutare a indicare il rendiconto, il saldo o la riga del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="4188b-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="4188b-116">Tuttavia, è improbabile che tali informazioni siano sufficienti per identificare il campo o l'elemento che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="4188b-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="4188b-117">Quali sono le differenze?</span><span class="sxs-lookup"><span data-stu-id="4188b-117">What are the differences?</span></span>
<span data-ttu-id="4188b-118">Confrontare la definizione del layout del file bancario con la definizione di importazione di Finance and Operations e osservare tutte le differenze nei campi e le voci.</span><span class="sxs-lookup"><span data-stu-id="4188b-118">Compare the bank file layout definition to the Finance and Operations import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="4188b-119">Confrontare il file di rendiconto bancario al file di esempio di Finance and Operations correlato.</span><span class="sxs-lookup"><span data-stu-id="4188b-119">Compare the bank statement file to the related sample Finance and Operations file.</span></span> <span data-ttu-id="4188b-120">Nei file ISO20022, tutte le differenze dovrebbero essere semplici da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="4188b-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="transformations"></a><span data-ttu-id="4188b-121">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="4188b-121">Transformations</span></span>
<span data-ttu-id="4188b-122">In genere, la modifica deve essere eseguita in una delle tre trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="4188b-122">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="4188b-123">Ogni trasformazione viene scritta per uno specifico standard.</span><span class="sxs-lookup"><span data-stu-id="4188b-123">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="4188b-124">Nome risorsa</span><span class="sxs-lookup"><span data-stu-id="4188b-124">Resource name</span></span>                                         | <span data-ttu-id="4188b-125">Nome file</span><span class="sxs-lookup"><span data-stu-id="4188b-125">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="4188b-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="4188b-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="4188b-127">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="4188b-127">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="4188b-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="4188b-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="4188b-129">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="4188b-129">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="4188b-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="4188b-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="4188b-131">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="4188b-131">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="4188b-132">Debug delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="4188b-132">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="4188b-133">Modificare i file BAI2 e MT940</span><span class="sxs-lookup"><span data-stu-id="4188b-133">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="4188b-134">I file BAI2 e MT940 sono file di testo e richiedono una modifica per attivare il debug del linguaggio XSLT (Extensible Stylesheet Language Transformation).</span><span class="sxs-lookup"><span data-stu-id="4188b-134">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="4188b-135">La modifica viene eseguita automaticamente quando un file viene importato.</span><span class="sxs-lookup"><span data-stu-id="4188b-135">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="4188b-136">Creare un file XML e copiare il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="4188b-136">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="4188b-137">Copiare il contenuto del file di rendiconto bancario e incollarlo nel file XML in modo da sostituire **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="4188b-137">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="4188b-138">Debug di XSLT</span><span class="sxs-lookup"><span data-stu-id="4188b-138">Debug the XSLT</span></span>

<span data-ttu-id="4188b-139">Per ulteriori informazioni, vedere <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="4188b-139">For more information, see <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="4188b-140">Avviare Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4188b-140">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="4188b-141">Creare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="4188b-141">Create a console application.</span></span>
3.  <span data-ttu-id="4188b-142">Aprire l'elemento XSLT appropriato.</span><span class="sxs-lookup"><span data-stu-id="4188b-142">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="4188b-143">Fare clic sull'elemento XLST e la relativa pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4188b-143">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="4188b-144">Impostare l'input sul percorso del file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="4188b-144">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="4188b-145">Definire un percorso il nome file per l'output.</span><span class="sxs-lookup"><span data-stu-id="4188b-145">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="4188b-146">Impostare i punti di interruzione necessari.</span><span class="sxs-lookup"><span data-stu-id="4188b-146">Set the required break points.</span></span>
8.  <span data-ttu-id="4188b-147">Nel menu fare clic su **XML** &gt; **Avvia debug XSLT**.</span><span class="sxs-lookup"><span data-stu-id="4188b-147">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="4188b-148">Formattare l'output XSLT</span><span class="sxs-lookup"><span data-stu-id="4188b-148">Format the XSLT output</span></span>

<span data-ttu-id="4188b-149">Quando la trasformazione viene eseguita, creare un file di output da visualizzare in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4188b-149">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="4188b-150">Utilizzare CTRL+A, CTRL+K e CTRL+D per formattare rapidamente il file di output.</span><span class="sxs-lookup"><span data-stu-id="4188b-150">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="4188b-151">Modificare la trasformazione</span><span class="sxs-lookup"><span data-stu-id="4188b-151">Adjust the transformation</span></span>

<span data-ttu-id="4188b-152">Modificare la trasformazione per ottenere il campo o l'elemento appropriato nel file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="4188b-152">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="4188b-153">Quindi mappare il campo o l'elemento all'elemento appropriato di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4188b-153">Then map that field or element to the appropriate Finance and Operations element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="4188b-154">Indicatore Dare/Avere</span><span class="sxs-lookup"><span data-stu-id="4188b-154">Debit/credit indicator</span></span>

<span data-ttu-id="4188b-155">Talvolta, importi Dare potrebbero essere importati come voci Avere e viceversa.</span><span class="sxs-lookup"><span data-stu-id="4188b-155">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="4188b-156">Per risolvere questo problema, è necessario modificare la trasformazione XSLT appropriata.</span><span class="sxs-lookup"><span data-stu-id="4188b-156">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="4188b-157">Se i rendiconti bancari provengono da banche diverse, verificare che utilizzino tutti lo stesso approccio in termini di importi Dare/Avere o creare trasformazioni separate.</span><span class="sxs-lookup"><span data-stu-id="4188b-157">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="4188b-158">Modello BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="4188b-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="4188b-159">Modello ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="4188b-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="4188b-160">Modello MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="4188b-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="4188b-161">Esempi di formati di rendiconto bancario e di layout tecnici</span><span class="sxs-lookup"><span data-stu-id="4188b-161">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="4188b-162">Nella tabella seguente vengono elencati esempi di definizioni di layout tecnici per file di importazione di riconciliazione bancaria e tre file di esempio di rendiconti bancari correlati.</span><span class="sxs-lookup"><span data-stu-id="4188b-162">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="4188b-163">È possibile scaricare i file di esempio e i layout tecnici a questo indirizzo: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="4188b-163">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="4188b-164">Definizione di layout tecnico</span><span class="sxs-lookup"><span data-stu-id="4188b-164">Technical layout definition</span></span>                             | <span data-ttu-id="4188b-165">File di esempio di rendiconto bancario</span><span class="sxs-lookup"><span data-stu-id="4188b-165">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="4188b-166">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="4188b-166">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="4188b-167">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="4188b-167">MT940StatementExample</span></span>                |
| <span data-ttu-id="4188b-168">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="4188b-168">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="4188b-169">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="4188b-169">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="4188b-170">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="4188b-170">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="4188b-171">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="4188b-171">BAI2StatementExample</span></span>                 |






