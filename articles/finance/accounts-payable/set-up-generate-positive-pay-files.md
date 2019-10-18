---
title: Impostare e generare file pagamenti sicuri
description: In questo argomento viene descritto come impostare un pagamento sicuro e generare file pagamenti sicuri.
author: abruer
manager: AnnBe
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 600e3279536857dbb804ef420572fad42fe72311
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189524"
---
# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="a498f-103">Impostare e generare file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-103">Set up and generate positive pay files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a498f-104">In questo argomento viene descritto come impostare un pagamento sicuro e generare file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-104">This topic explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="a498f-105">Impostare il pagamento sicuro per generare l'elenco elettronico degli assegni che viene fornito alla banca.</span><span class="sxs-lookup"><span data-stu-id="a498f-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="a498f-106">Quando si presenta un assegno alla banca, la banca lo confronta con l'elenco degli assegni.</span><span class="sxs-lookup"><span data-stu-id="a498f-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="a498f-107">Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida.</span><span class="sxs-lookup"><span data-stu-id="a498f-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="a498f-108">Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.</span><span class="sxs-lookup"><span data-stu-id="a498f-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="a498f-109">Sicurezza dei file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-109">Security for positive pay files</span></span>
<span data-ttu-id="a498f-110">I file pagamenti sicuri possono contenere dati riservati sui beneficiari e sugli importi dell'assegno.</span><span class="sxs-lookup"><span data-stu-id="a498f-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="a498f-111">Di conseguenza, assicurarsi di utilizzare le misure di sicurezza appropriate dalla generazione dei file fino alla loro ricezione da parte della banca.</span><span class="sxs-lookup"><span data-stu-id="a498f-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="a498f-112">I file pagamenti sicuri vengono scaricati nel percorso specificato dal Web browser.</span><span class="sxs-lookup"><span data-stu-id="a498f-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="a498f-113">Poiché i file pagamenti sicuri possono contenere informazioni riservate, è importante che solo gli utenti autorizzati abbiano accesso per generare e visualizzare queste informazioni in Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="a498f-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="a498f-114">Utilizzare la seguente tabella per determinare i privilegi necessari.</span><span class="sxs-lookup"><span data-stu-id="a498f-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a498f-115">Attività</span><span class="sxs-lookup"><span data-stu-id="a498f-115">Task</span></span></th>
<th><span data-ttu-id="a498f-116">Privilegio</span><span class="sxs-lookup"><span data-stu-id="a498f-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a498f-117">Generare i file pagamenti sicuri dalla pagina elenco <strong>Conti bancari</strong> o dalla pagina <strong>Conti bancari</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498f-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="a498f-118"><strong>Gestisci informazioni su pagamenti sicuri bancari</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="a498f-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="a498f-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="a498f-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498f-120">Generare file pagamenti sicuri per più persone giuridiche e conti bancari dalla pagina <strong>Genera un file pagamenti sicuri</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498f-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="a498f-121"><strong>Gestisci informazioni su pagamenti sicuri bancari</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="a498f-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="a498f-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="a498f-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498f-123">Visualizzare i file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498f-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="a498f-124"><strong>Visualizza le informazioni sui pagamenti sicuri per più persone giuridiche</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="a498f-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498f-125">Confermare un file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498f-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="a498f-126"><strong>Conferma file pagamenti sicuri</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="a498f-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498f-127">Richiamare un file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498f-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="a498f-128"><strong>Richiama file pagamenti sicuri</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="a498f-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="a498f-129">Impostare un formato pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-129">Set up a positive pay format</span></span>
<span data-ttu-id="a498f-130">Questi file vengono creati tramite entità di dati.</span><span class="sxs-lookup"><span data-stu-id="a498f-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="a498f-131">Prima di generare un file pagamenti sicuri, è necessario impostare un formato di input trasformazione da utilizzare per convertire le informazioni sull'assegno in un formato interpretabile dalla banca.</span><span class="sxs-lookup"><span data-stu-id="a498f-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="a498f-132">Nella pagina **Formato pagamenti sicuri** è possibile creare un identificatore di formato file e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a498f-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="a498f-133">Il formato di input trasformazione deve essere del tipo XML.</span><span class="sxs-lookup"><span data-stu-id="a498f-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="a498f-134">Il formato specifico dipende dal file di trasformazione in uso.</span><span class="sxs-lookup"><span data-stu-id="a498f-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="a498f-135">Ad esempio, il file di esempio XSLT (Extensible Stylesheet Language Transformations) fornito usa il formato **XML-Element**.</span><span class="sxs-lookup"><span data-stu-id="a498f-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="a498f-136">Utilizzare l'azione **Carica file utilizzati per la trasformazione** per specificare il percorso del file di trasformazione per il formato richiesto dalla banca.</span><span class="sxs-lookup"><span data-stu-id="a498f-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="a498f-137">Esempio: file XSLT per il file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-137">Example: XSLT file for positive pay file</span></span>
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="a498f-138">Assegnare il formato pagamenti sicuri a un conto bancario</span><span class="sxs-lookup"><span data-stu-id="a498f-138">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="a498f-139">Per ogni conto bancario per il quale generare le informazioni pagamenti sicuri, è necessario assegnare il formato pagamenti sicuri specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="a498f-139">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="a498f-140">Nella pagina **Conti bancari** selezionare il formato pagamenti sicuri che corrisponde al conto bancario.</span><span class="sxs-lookup"><span data-stu-id="a498f-140">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="a498f-141">Nel campo **Data di inizio pagamenti sicuri** immettere la prima data per generare i file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-141">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="a498f-142">È importante immettere una data in questo campo.</span><span class="sxs-lookup"><span data-stu-id="a498f-142">It's important that you enter a date in this field.</span></span> <span data-ttu-id="a498f-143">In caso contrario, il file pagamenti sicuri generato includerà tutti gli assegni creati per questo conto bancario.</span><span class="sxs-lookup"><span data-stu-id="a498f-143">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="a498f-144">Assegnare una sequenza numerica per i file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-144">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="a498f-145">Ogni file pagamenti sicuri deve essere dotato di un numero univoco.</span><span class="sxs-lookup"><span data-stu-id="a498f-145">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="a498f-146">Utilizzare la scheda **Sequenze numeriche** nella pagina **Parametri di gestione cassa e banche** per creare una sequenza numerica per i file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-146">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="a498f-147">Generare un file pagamenti sicuri per un singolo conto bancario</span><span class="sxs-lookup"><span data-stu-id="a498f-147">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="a498f-148">È possibile generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario.</span><span class="sxs-lookup"><span data-stu-id="a498f-148">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="a498f-149">Per informazioni su come generare contemporaneamente file pagamenti sicuri per più persone giuridiche e conti bancari, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="a498f-149">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="a498f-150">Per generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario, aprire la finestra di dialogo **Genera un file pagamenti sicuri** dalla pagina **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="a498f-150">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="a498f-151">Nel campo **Data limite** immettere l'ultima data dell'assegno da includere nel file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-151">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="a498f-152">Tutti gli assegni che non sono stati inclusi in un file pagamenti sicuri entro questa data vengono inclusi nel file.</span><span class="sxs-lookup"><span data-stu-id="a498f-152">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="a498f-153">Generare un file pagamenti sicuri per più conti bancari</span><span class="sxs-lookup"><span data-stu-id="a498f-153">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="a498f-154">Per generare un file pagamenti sicuri per più conti bancari, utilizzare l'attività periodica **Genera un file pagamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="a498f-154">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="a498f-155">Selezionare il formato pagamenti sicuri per il file e specificare se generare il file per tutte le persone giuridiche o per una persona giuridica selezionata.</span><span class="sxs-lookup"><span data-stu-id="a498f-155">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="a498f-156">È anche possibile generare il file pagamenti sicuri per tutti i conti bancari che utilizzano il formato specificato o per un conto bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="a498f-156">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="a498f-157">Nel campo **Data limite** immettere l'ultima data dell'assegno da includere nel file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-157">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="a498f-158">Tutti gli assegni che non sono stati inclusi in un file pagamenti sicuri entro questa data vengono inclusi nel file.</span><span class="sxs-lookup"><span data-stu-id="a498f-158">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="a498f-159">Visualizzare i risultati della generazione del file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-159">View the results of positive pay file generation</span></span>
<span data-ttu-id="a498f-160">Dopo che il file pagamenti sicuri è stato generato, è possibile visualizzare i risultati nella pagina **Riepilogo file pagamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="a498f-160">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="a498f-161">Per visualizzare i dettagli dei singoli assegni, utilizzare la pagina dei dettagli **File pagamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="a498f-161">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="a498f-162">Conferma un file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-162">Confirm a positive pay file</span></span>
<span data-ttu-id="a498f-163">Dopo aver pagato gli assegni elencati in un file pagamenti sicuri, viene visualizzato un numero di conferma dalla banca.</span><span class="sxs-lookup"><span data-stu-id="a498f-163">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="a498f-164">È quindi possibile confermare il file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-164">You can then confirm the positive pay file.</span></span> <span data-ttu-id="a498f-165">Nella pagina **Riepilogo file pagamenti sicuri**, selezionare un file pagamenti sicuri con stato **Creato**, quindi selezionare l'azione **Immetti conferma**.</span><span class="sxs-lookup"><span data-stu-id="a498f-165">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="a498f-166">Quando si conferma un file pagamenti sicuri, viene registrato il numero di conferma ricevuto dalla banca.</span><span class="sxs-lookup"><span data-stu-id="a498f-166">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="a498f-167">Richiamare un file pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="a498f-167">Recall a positive pay file</span></span>
<span data-ttu-id="a498f-168">Per modificare un file pagamenti sicuri, è possibile richiamarlo.</span><span class="sxs-lookup"><span data-stu-id="a498f-168">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="a498f-169">Nella pagina **Riepilogo file pagamenti sicuri**, selezionare un file pagamenti sicuri con stato **Creato**, quindi selezionare l'azione **Immetti conferma**.</span><span class="sxs-lookup"><span data-stu-id="a498f-169">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="a498f-170">Per ogni assegno nel file pagamenti sicuri, viene reimpostato il campo che indica se l'assegno è stato incluso in un file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="a498f-170">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="a498f-171">È quindi possibile creare un nuovo file pagamenti sicuri che includa l'assegno richiamato.</span><span class="sxs-lookup"><span data-stu-id="a498f-171">You can then create a new positive pay file that includes the check that was recalled.</span></span>



