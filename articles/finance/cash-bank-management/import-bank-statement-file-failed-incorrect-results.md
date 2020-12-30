---
title: Risoluzione dei problemi di importazione di file di rendiconto bancario
description: È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.
author: panolte
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09b24b88ee5f8104aabd11397d5bd2745e846cb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444664"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="aaa37-107">Risoluzione dei problemi di importazione di file di rendiconto bancario</span><span class="sxs-lookup"><span data-stu-id="aaa37-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aaa37-108">È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="aaa37-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="aaa37-109">A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="aaa37-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="aaa37-110">Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="aaa37-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="aaa37-111">In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="aaa37-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="aaa37-112">In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="aaa37-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="aaa37-113">Qual è l'errore?</span><span class="sxs-lookup"><span data-stu-id="aaa37-113">What is the error?</span></span>
------------------

<span data-ttu-id="aaa37-114">Dopo aver tentato di importare un file di rendiconto bancario, passare allo storici processi della gestione dati e ai dettagli di esecuzione per individuare l'errore.</span><span class="sxs-lookup"><span data-stu-id="aaa37-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="aaa37-115">L'errore potrà aiutare a indicare il rendiconto, il saldo o la riga del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="aaa37-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="aaa37-116">Tuttavia, è improbabile che tali informazioni siano sufficienti per identificare il campo o l'elemento che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="aaa37-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="aaa37-117">Quali sono le differenze?</span><span class="sxs-lookup"><span data-stu-id="aaa37-117">What are the differences?</span></span>
<span data-ttu-id="aaa37-118">Confrontare la definizione del layout del file bancario con la definizione di importazione di Finance e osservare tutte le differenze nei campi e le voci.</span><span class="sxs-lookup"><span data-stu-id="aaa37-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="aaa37-119">Confrontare il file di rendiconto bancario al file di esempio di Finance correlato.</span><span class="sxs-lookup"><span data-stu-id="aaa37-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="aaa37-120">Nei file ISO20022, tutte le differenze dovrebbero essere semplici da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="aaa37-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="aaa37-121">Differenze di fuso orario nei rendiconti bancari importati</span><span class="sxs-lookup"><span data-stu-id="aaa37-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="aaa37-122">I valori di data e ora nel file di importazione possono variare in base ai valori di data e ora visualizzati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aaa37-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="aaa37-123">Per impedire questa discrepanza, immettere una preferenze di fuso orario nella pagina **Configura origine dati**.</span><span class="sxs-lookup"><span data-stu-id="aaa37-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="aaa37-124">Per ulteriori informazioni sull'immissione di una preferenze di fuso orario, vedere [Impostare il processo di importazione della riconciliazione estratti conto avanzata](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="aaa37-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="aaa37-125">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="aaa37-125">Transformations</span></span>
<span data-ttu-id="aaa37-126">In genere, la modifica deve essere eseguita in una delle tre trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="aaa37-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="aaa37-127">Ogni trasformazione viene scritta per uno specifico standard.</span><span class="sxs-lookup"><span data-stu-id="aaa37-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="aaa37-128">Nome risorsa</span><span class="sxs-lookup"><span data-stu-id="aaa37-128">Resource name</span></span>                                         | <span data-ttu-id="aaa37-129">Nome file</span><span class="sxs-lookup"><span data-stu-id="aaa37-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="aaa37-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="aaa37-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="aaa37-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="aaa37-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="aaa37-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="aaa37-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="aaa37-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="aaa37-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="aaa37-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="aaa37-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="aaa37-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="aaa37-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="aaa37-136">Debug delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="aaa37-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="aaa37-137">Modificare i file BAI2 e MT940</span><span class="sxs-lookup"><span data-stu-id="aaa37-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="aaa37-138">I file BAI2 e MT940 sono file di testo e richiedono una modifica per attivare il debug del linguaggio XSLT (Extensible Stylesheet Language Transformation).</span><span class="sxs-lookup"><span data-stu-id="aaa37-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="aaa37-139">La modifica viene eseguita automaticamente quando un file viene importato.</span><span class="sxs-lookup"><span data-stu-id="aaa37-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="aaa37-140">Creare un file XML e copiare il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="aaa37-140">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="aaa37-141">Copiare il contenuto del file di rendiconto bancario e incollarlo nel file XML in modo da sostituire **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="aaa37-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="aaa37-142">Debug di XSLT</span><span class="sxs-lookup"><span data-stu-id="aaa37-142">Debug the XSLT</span></span>

<span data-ttu-id="aaa37-143">Per ulteriori informazioni, vedere <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="aaa37-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="aaa37-144">Avviare Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aaa37-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="aaa37-145">Creare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="aaa37-145">Create a console application.</span></span>
3.  <span data-ttu-id="aaa37-146">Aprire l'elemento XSLT appropriato.</span><span class="sxs-lookup"><span data-stu-id="aaa37-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="aaa37-147">Fare clic sull'elemento XLST e la relativa pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="aaa37-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="aaa37-148">Impostare l'input sul percorso del file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="aaa37-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="aaa37-149">Definire un percorso il nome file per l'output.</span><span class="sxs-lookup"><span data-stu-id="aaa37-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="aaa37-150">Impostare i punti di interruzione necessari.</span><span class="sxs-lookup"><span data-stu-id="aaa37-150">Set the required break points.</span></span>
8.  <span data-ttu-id="aaa37-151">Nel menu fare clic su **XML** &gt; **Avvia debug XSLT**.</span><span class="sxs-lookup"><span data-stu-id="aaa37-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="aaa37-152">Formattare l'output XSLT</span><span class="sxs-lookup"><span data-stu-id="aaa37-152">Format the XSLT output</span></span>

<span data-ttu-id="aaa37-153">Quando la trasformazione viene eseguita, creare un file di output da visualizzare in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aaa37-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="aaa37-154">Utilizzare CTRL+A, CTRL+K e CTRL+D per formattare rapidamente il file di output.</span><span class="sxs-lookup"><span data-stu-id="aaa37-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="aaa37-155">Modificare la trasformazione</span><span class="sxs-lookup"><span data-stu-id="aaa37-155">Adjust the transformation</span></span>

<span data-ttu-id="aaa37-156">Modificare la trasformazione per ottenere il campo o l'elemento appropriato nel file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="aaa37-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="aaa37-157">Quindi mappare il campo o l'elemento all'elemento appropriato di Finance.</span><span class="sxs-lookup"><span data-stu-id="aaa37-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="aaa37-158">Indicatore Dare/Avere</span><span class="sxs-lookup"><span data-stu-id="aaa37-158">Debit/credit indicator</span></span>

<span data-ttu-id="aaa37-159">Talvolta, importi Dare potrebbero essere importati come voci Avere e viceversa.</span><span class="sxs-lookup"><span data-stu-id="aaa37-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="aaa37-160">Per risolvere questo problema, è necessario modificare la trasformazione XSLT appropriata.</span><span class="sxs-lookup"><span data-stu-id="aaa37-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="aaa37-161">Se i rendiconti bancari provengono da banche diverse, verificare che utilizzino tutti lo stesso approccio in termini di importi Dare/Avere o creare trasformazioni separate.</span><span class="sxs-lookup"><span data-stu-id="aaa37-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="aaa37-162">Modello BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="aaa37-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="aaa37-163">Modello ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="aaa37-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="aaa37-164">Modello MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="aaa37-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="aaa37-165">Esempi di formati di rendiconto bancario e di layout tecnici</span><span class="sxs-lookup"><span data-stu-id="aaa37-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="aaa37-166">Nella tabella seguente vengono elencati esempi di definizioni di layout tecnici per file di importazione di riconciliazione bancaria e tre file di esempio di rendiconti bancari correlati.</span><span class="sxs-lookup"><span data-stu-id="aaa37-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="aaa37-167">È possibile scaricare i file di esempio e layout tecnici qui: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="aaa37-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="aaa37-168">Definizione di layout tecnico</span><span class="sxs-lookup"><span data-stu-id="aaa37-168">Technical layout definition</span></span>                             | <span data-ttu-id="aaa37-169">File di esempio di rendiconto bancario</span><span class="sxs-lookup"><span data-stu-id="aaa37-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="aaa37-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="aaa37-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="aaa37-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="aaa37-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="aaa37-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="aaa37-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="aaa37-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="aaa37-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="aaa37-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="aaa37-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="aaa37-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="aaa37-175">BAI2StatementExample</span></span>                 |





