---
title: Risoluzione dei problemi di importazione di file di rendiconto bancario
description: È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0e01881a6b68526479d27014d49a718069cffc9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815886"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="9e7ef-107">Risoluzione dei problemi di importazione di file di rendiconto bancario</span><span class="sxs-lookup"><span data-stu-id="9e7ef-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e7ef-108">È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="9e7ef-109">A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="9e7ef-110">Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="9e7ef-111">In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="9e7ef-112">In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="9e7ef-113">Qual è l'errore?</span><span class="sxs-lookup"><span data-stu-id="9e7ef-113">What is the error?</span></span>
------------------

<span data-ttu-id="9e7ef-114">Dopo aver tentato di importare un file di rendiconto bancario, passare allo storici processi della gestione dati e ai dettagli di esecuzione per individuare l'errore.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="9e7ef-115">L'errore potrà aiutare a indicare il rendiconto, il saldo o la riga del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="9e7ef-116">Tuttavia, è improbabile che tali informazioni siano sufficienti per identificare il campo o l'elemento che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7ef-117">Gli estratti conto bancari importati possono sovrapporsi solo per un singolo punto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="9e7ef-118">Ad esempio, se un rendiconto termina alle 12:00 AM del 1° gennaio 2021, la data di inizio del rendiconto successivo può essere 12:00 AM del 1° gennaio, 2021 12:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="9e7ef-119">Quali sono le differenze?</span><span class="sxs-lookup"><span data-stu-id="9e7ef-119">What are the differences?</span></span>
<span data-ttu-id="9e7ef-120">Confrontare la definizione del layout del file bancario con la definizione di importazione di Finance e osservare tutte le differenze nei campi e le voci.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="9e7ef-121">Confrontare il file di rendiconto bancario al file di esempio di Finance correlato.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="9e7ef-122">Nei file ISO20022, tutte le differenze dovrebbero essere semplici da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="9e7ef-123">Differenze di fuso orario nei rendiconti bancari importati</span><span class="sxs-lookup"><span data-stu-id="9e7ef-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="9e7ef-124">I valori di data e ora nel file di importazione possono variare in base ai valori di data e ora visualizzati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="9e7ef-125">Per impedire questa discrepanza, immettere una preferenze di fuso orario nella pagina **Configura origine dati**.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="9e7ef-126">Per ulteriori informazioni sull'immissione di una preferenze di fuso orario, vedi [Impostare il processo di importazione della riconciliazione estratti conto avanzata](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="9e7ef-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="9e7ef-127">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="9e7ef-127">Transformations</span></span>
<span data-ttu-id="9e7ef-128">In genere, la modifica deve essere eseguita in una delle tre trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="9e7ef-129">Ogni trasformazione viene scritta per uno specifico standard.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="9e7ef-130">Nome risorsa</span><span class="sxs-lookup"><span data-stu-id="9e7ef-130">Resource name</span></span>                                         | <span data-ttu-id="9e7ef-131">Nome file</span><span class="sxs-lookup"><span data-stu-id="9e7ef-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="9e7ef-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="9e7ef-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="9e7ef-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="9e7ef-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="9e7ef-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="9e7ef-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="9e7ef-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="9e7ef-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="9e7ef-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="9e7ef-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="9e7ef-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="9e7ef-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="9e7ef-138">Debug delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="9e7ef-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="9e7ef-139">Modificare i file BAI2 e MT940</span><span class="sxs-lookup"><span data-stu-id="9e7ef-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="9e7ef-140">I file BAI2 e MT940 sono file di testo e richiedono una modifica per attivare il debug del linguaggio XSLT (Extensible Stylesheet Language Transformation).</span><span class="sxs-lookup"><span data-stu-id="9e7ef-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="9e7ef-141">La modifica viene eseguita automaticamente quando un file viene importato.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="9e7ef-142">Creare un file XML e copiare il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="9e7ef-143">Copiare il contenuto del file di rendiconto bancario e incollarlo nel file XML in modo da sostituire **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="9e7ef-144">Debug di XSLT</span><span class="sxs-lookup"><span data-stu-id="9e7ef-144">Debug the XSLT</span></span>

<span data-ttu-id="9e7ef-145">Per ulteriori informazioni, vedere <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="9e7ef-146">Avviare Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="9e7ef-147">Creare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-147">Create a console application.</span></span>
3.  <span data-ttu-id="9e7ef-148">Aprire l'elemento XSLT appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="9e7ef-149">Fare clic sull'elemento XLST e la relativa pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="9e7ef-150">Impostare l'input sul percorso del file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="9e7ef-151">Definire un percorso il nome file per l'output.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="9e7ef-152">Impostare i punti di interruzione necessari.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-152">Set the required break points.</span></span>
8.  <span data-ttu-id="9e7ef-153">Nel menu fare clic su **XML** &gt; **Avvia debug XSLT**.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="9e7ef-154">Formattare l'output XSLT</span><span class="sxs-lookup"><span data-stu-id="9e7ef-154">Format the XSLT output</span></span>

<span data-ttu-id="9e7ef-155">Quando la trasformazione viene eseguita, creare un file di output da visualizzare in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="9e7ef-156">Utilizzare CTRL+A, CTRL+K e CTRL+D per formattare rapidamente il file di output.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="9e7ef-157">Modificare la trasformazione</span><span class="sxs-lookup"><span data-stu-id="9e7ef-157">Adjust the transformation</span></span>

<span data-ttu-id="9e7ef-158">Modificare la trasformazione per ottenere il campo o l'elemento appropriato nel file di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="9e7ef-159">Quindi mappare il campo o l'elemento all'elemento appropriato di Finance.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="9e7ef-160">Indicatore Dare/Avere</span><span class="sxs-lookup"><span data-stu-id="9e7ef-160">Debit/credit indicator</span></span>

<span data-ttu-id="9e7ef-161">Talvolta, importi Dare potrebbero essere importati come voci Avere e viceversa.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="9e7ef-162">Per risolvere questo problema, è necessario modificare la trasformazione XSLT appropriata.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="9e7ef-163">Se i rendiconti bancari provengono da banche diverse, verificare che utilizzino tutti lo stesso approccio in termini di importi Dare/Avere o creare trasformazioni separate.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="9e7ef-164">Modello BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="9e7ef-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="9e7ef-165">Modello ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="9e7ef-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="9e7ef-166">Modello MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="9e7ef-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="9e7ef-167">Esempi di formati di rendiconto bancario e di layout tecnici</span><span class="sxs-lookup"><span data-stu-id="9e7ef-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="9e7ef-168">Nella tabella seguente vengono elencati esempi di definizioni di layout tecnici per file di importazione di riconciliazione bancaria e tre file di esempio di rendiconti bancari correlati.</span><span class="sxs-lookup"><span data-stu-id="9e7ef-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="9e7ef-169">È possibile scaricare i file di esempio e layout tecnici qui: [Importare file di esempio](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="9e7ef-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="9e7ef-170">Definizione di layout tecnico</span><span class="sxs-lookup"><span data-stu-id="9e7ef-170">Technical layout definition</span></span>                             | <span data-ttu-id="9e7ef-171">File di esempio di rendiconto bancario</span><span class="sxs-lookup"><span data-stu-id="9e7ef-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="9e7ef-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="9e7ef-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="9e7ef-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="9e7ef-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="9e7ef-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="9e7ef-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="9e7ef-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="9e7ef-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="9e7ef-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="9e7ef-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="9e7ef-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="9e7ef-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
