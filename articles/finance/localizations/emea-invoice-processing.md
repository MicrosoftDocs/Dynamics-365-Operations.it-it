---
title: Elaborazione fattura
description: In questo argomento vengono fornite informazioni sull'elaborazione delle fatture per l'Europa orientale.
author: v-kikozl
manager: AnnBe
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia, Italy
ms.author: v-kikozl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 87a06e1b17e9c0bdb4147f49b2dacb74236360fa
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039906"
---
# <a name="invoice-processing"></a><span data-ttu-id="e358b-103">Elaborazione fattura</span><span class="sxs-lookup"><span data-stu-id="e358b-103">Invoice processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e358b-104">Questo argomento descrive brevemente alcuni scenari specifici del paese, come l'imposta sul valore aggiunto (IVA) intracomunitaria e l'imposta differita.</span><span class="sxs-lookup"><span data-stu-id="e358b-104">This topic briefly describes some country-specific scenarios, such as intra-community value-added tax (VAT) and deferred tax.</span></span> <span data-ttu-id="e358b-105">I requisiti legali per alcuni paesi europei influenzano il processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="e358b-105">Legal requirements for some European countries affect the invoicing process.</span></span> <span data-ttu-id="e358b-106">Questo argomento fornisce anche informazioni su come vengono elaborate le fatture dei clienti e dei fornitori per questi paesi.</span><span class="sxs-lookup"><span data-stu-id="e358b-106">This topic also provides information about how customer and vendor invoices are processed for these countries.</span></span> 
<table>
<thead>
<tr>
<th><span data-ttu-id="e358b-107">Scenario</span><span class="sxs-lookup"><span data-stu-id="e358b-107">Scenario</span></span></th>
<th><span data-ttu-id="e358b-108">Paesi</span><span class="sxs-lookup"><span data-stu-id="e358b-108">Countries</span></span></th>
<th><span data-ttu-id="e358b-109">Descrizione delle modifiche della funzionalità</span><span class="sxs-lookup"><span data-stu-id="e358b-109">Description of the functionality changes</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e358b-110">Date di Contabilità fornitori e Contabilità clienti per IVA</span><span class="sxs-lookup"><span data-stu-id="e358b-110">Accounts receivable and Accounts payable dates for VAT</span></span></td>
<td><span data-ttu-id="e358b-111">Repubblica Ceca, Polonia</span><span class="sxs-lookup"><span data-stu-id="e358b-111">Czech Republic, Poland</span></span></td>
<td>
<p><span data-ttu-id="e358b-112">Quando le merci vengono acquistate da paesi dell'Unione Europea (UE), c'è l'obbligo di autovalutazione dell'IVA:</span><span class="sxs-lookup"><span data-stu-id="e358b-112">When goods are purchased from European Union (EU) countries, there is an obligation of self-assessment of VAT:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-113">L'IVA a debito deve essere pagata nel periodo IVA in cui è stata emessa la fattura (data del documento).</span><span class="sxs-lookup"><span data-stu-id="e358b-113">The output VAT must be paid in a VAT period where the invoice was issued (document date).</span></span></li>
<li><span data-ttu-id="e358b-114">L'IVA a credito non può essere detratta prima del ricevimento del documento (data del registro IVA).</span><span class="sxs-lookup"><span data-stu-id="e358b-114">The input VAT can’t be deducted before the document receipt (VAT register date).</span></span></li>
</ul>
<p><span data-ttu-id="e358b-115">Le seguenti impostazioni devono essere configurate per supportare questo scenario:</span><span class="sxs-lookup"><span data-stu-id="e358b-115">The following settings should be configured to support this scenario:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-116">Nella pagina <strong>Parametri contabilità fornitori</strong> abilitare i parametri <strong>IVA intracomunitaria</strong> e <strong>Data documento per IVA intracomunitaria</strong>.</span><span class="sxs-lookup"><span data-stu-id="e358b-116">On the <strong>Accounts payable parameters</strong> page, enable the <strong>Intra-community VAT</strong> and <strong>Document date for intra-community VAT</strong> parameters.</span></span></li>
<li><span data-ttu-id="e358b-117">Impostare due codici IVA, uno con una percentuale di IVA positiva e uno con una percentuale di IVA negativa.</span><span class="sxs-lookup"><span data-stu-id="e358b-117">Set up two sales tax codes, one that has a positive sales tax percentage and one that has a negative sales tax percentage.</span></span></li>
<li><span data-ttu-id="e358b-118">Impostare una fascia IVA che include il codice IVA positiva e negativa.</span><span class="sxs-lookup"><span data-stu-id="e358b-118">Set up a sales tax group that includes both the positive and negative sales tax codes.</span></span> <span data-ttu-id="e358b-119">Per il codice IVA negativa, impostare il parametro <strong>IVA intracomunitaria</strong> su <strong>Sì</strong>.</span><span class="sxs-lookup"><span data-stu-id="e358b-119">For the negative sales tax code, set the <strong>Intracommunity VAT</strong> parameter to <strong>Yes</strong>.</span></span></li>
</ul>
<p><span data-ttu-id="e358b-120">Dopo la corretta configurazione, gli acquisti avranno due transazioni IVA registrate:</span><span class="sxs-lookup"><span data-stu-id="e358b-120">After successful setup, purchases will have two posted sales tax transactions:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-121">Una transazione positiva che ha una direzione di <strong>IVA a credito</strong> e una data del registro IVA che sia uguale alla data dalla pagina di registrazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="e358b-121">A positive transaction that has a direction of <strong>sales tax receivable</strong> and a VAT register date that equals the date from the invoice posting page.</span></span></li>
<li><span data-ttu-id="e358b-122">Una transazione negativa che ha una direzione di <strong>IVA a debito</strong> e una data del registro IVA che sia uguale alla data del documento.</span><span class="sxs-lookup"><span data-stu-id="e358b-122">A negative transaction that has a direction of <strong>sales tax payable</strong> and a VAT register date that equals the document date.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="e358b-123">Modificare una data del documento di vendita.</span><span class="sxs-lookup"><span data-stu-id="e358b-123">Modify a sales document date.</span></span></td>
<td><span data-ttu-id="e358b-124">Tutti i paesi dell'Europa orientale</span><span class="sxs-lookup"><span data-stu-id="e358b-124">All Eastern European countries</span></span></td>
<td><p><span data-ttu-id="e358b-125">È possibile modificare il campo <strong>Data documento</strong> su una fattura di progetto.</span><span class="sxs-lookup"><span data-stu-id="e358b-125">You can modify the <strong>Document date</strong> field on a project invoice.</span></span> <span data-ttu-id="e358b-126">Questa data appare sulla fattura stampata.</span><span class="sxs-lookup"><span data-stu-id="e358b-126">This date appears on the printed invoice.</span></span></p>
<p><span data-ttu-id="e358b-127">C'è anche un campo <strong>Data documento</strong> nelle pagine <strong>Registrazione fattura</strong> e <strong>Fattura a testo libero</strong>.</span><span class="sxs-lookup"><span data-stu-id="e358b-127">There is also a <strong>Document date</strong> field on the <strong>Posting invoice</strong> and <strong>Free text invoice</strong> pages.</span></span> <span data-ttu-id="e358b-128">Dopo la registrazione di una fattura, la data del documento viene visualizzata nell'intestazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="e358b-128">After you post an invoice, the document date appears on the invoice header.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="e358b-129">Data documento per tasso di cambio</span><span class="sxs-lookup"><span data-stu-id="e358b-129">Document date for exchange rates</span></span></td>
<td><span data-ttu-id="e358b-130">Polonia, Ungheria, Repubblica Ceca, Italia</span><span class="sxs-lookup"><span data-stu-id="e358b-130">Poland, Hungary, Czech Republic, Italy</span></span></td>
<td>
<p><span data-ttu-id="e358b-131">La legislazione prevede regole diverse per la selezione di tassi di cambio validi per le transazioni commerciali.</span><span class="sxs-lookup"><span data-stu-id="e358b-131">Legislation provides different rules for selecting valid exchange rates for business transactions.</span></span> <span data-ttu-id="e358b-132">Nel campo <strong>Data tasso di cambio</strong> nelle pagine <strong>Parametri contabilità clienti</strong> e <strong>Parametri contabilità fornitori</strong> è possibile selezionare la data da utilizzare per gli importi nel calcolo della valuta contabile sui documenti di acquisto e di vendita.</span><span class="sxs-lookup"><span data-stu-id="e358b-132">In the <strong>Exchange rate date</strong> field on the <strong>Accounts receivable parameters</strong> and <strong>Accounts payable parameters</strong> pages, you can select the date that should be used for amounts in the accounting currency calculation on purchase and sales documents.</span></span> <span data-ttu-id="e358b-133">Durante l'immissione dei dati, il sistema recupera il tasso di cambio per la transazione, in base a questo parametro.</span><span class="sxs-lookup"><span data-stu-id="e358b-133">During data entry, the system retrieves the exchange rate for the transaction, based on this parameter.</span></span></p>
<blockquote>[!NOTE]<br><span data-ttu-id="e358b-134">Per l'Italia, questa funzionalità è applicabile solo nel modulo Contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="e358b-134">For Italy, this functionality is only applicable in the Accounts payable module.</span></span> <span data-ttu-id="e358b-135">Nei parametri della contabilità fornitori, un utente può selezionare <strong>Data registrazione</strong> o <strong>Data documento</strong> nel campo <strong>Data tasso di cambio</strong>.</span><span class="sxs-lookup"><span data-stu-id="e358b-135">In the Accounts payable parameters, a user can select <strong>Posting date</strong> or <strong>Document date</strong> in the <strong>Exchange rate date</strong> field.</span></span>   </blockquote>
<blockquote>[!NOTE]<br><span data-ttu-id="e358b-136">Quando si imposta il campo <strong>Data tasso di cambio</strong> su <strong>Data documento (solo per il commercio UE)</strong>, il sistema utilizza la fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="e358b-136">When you set the <strong>Exchange rate date</strong> field to <strong>Document date (for EU trade only)</strong>, the system uses the sales tax group.</span></span> <span data-ttu-id="e358b-137">Per la fascia IVA, esiste un parametro <strong>Commercio UE</strong> nella scheda <strong>Generale</strong>. Se l'opzione <strong>Commercio UE</strong> è impostata su <strong>Sì</strong> per la fascia IVA e se questa fascia IVA esiste nell'intestazione del documento, il sistema recupera il tasso di cambio in base alla data del documento.</span><span class="sxs-lookup"><span data-stu-id="e358b-137">For the sales tax group, there is a <strong>EU trade</strong> parameter on the <strong>General</strong> tab. If the <strong>EU trade</strong> option is set to <strong>Yes</strong> for the sales tax group, and if this sales tax group exists on the header of the document, the system retrieves the exchange rate based on the document date.</span></span> <span data-ttu-id="e358b-138">Se l'opzione <strong>Commercio UE</strong> è impostata su <strong>No</strong> per questa fascia IVA, il sistema recupera il tasso di cambio in base alla data di registrazione del documento.</span><span class="sxs-lookup"><span data-stu-id="e358b-138">If the <strong>EU trade</strong> option is set to <strong>No</strong> for this sales tax group, the system retrieves the exchange rate based on the posting date of the document.</span></span></blockquote>
</td>
</tr>
<tr>
<td><span data-ttu-id="e358b-139">Date commerciali, date del registro IVA e controllo della data di documenti e IVA</span><span class="sxs-lookup"><span data-stu-id="e358b-139">Trade dates, VAT register dates, and document and VAT date control</span></span></td>
<td><span data-ttu-id="e358b-140">Polonia, Ungheria, Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="e358b-140">Poland, Hungary, Czech Republic</span></span></td>
<td>
<p><span data-ttu-id="e358b-141">La data di vendita e la data di entrata del documento sono obbligatorie per il report IVA:</span><span class="sxs-lookup"><span data-stu-id="e358b-141">The sales date and the document receipt date are required for VAT reporting:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-142">La data di vendita è la data di evasione della transazione nella contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="e358b-142">The sales date is the fulfillment date of the transaction in Accounts receivable.</span></span></li>
<li><span data-ttu-id="e358b-143">La data di entrata del documento è una data che dimostra diritti di reclamare la detrazione dell'IVA nella contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="e358b-143">The document receipt date is a date that demonstrates the rights to claim a VAT deduction in Accounts payable.</span></span> <span data-ttu-id="e358b-144">Ogni documento ricevuto ha una data a fini del controllo.</span><span class="sxs-lookup"><span data-stu-id="e358b-144">Each document that is received has a date for audit purposes.</span></span></li>
</ul>
<p><span data-ttu-id="e358b-145">La funzionalità ungherese per le date di scadenza, la funzionalità ceca per le date di evasione e la funzionalità polacca per la data di registrazione dell'IVA includono il requisito per la dichiarazione fiscale che si basa su una data differente dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e358b-145">The Hungarian functionality for date deadlines, the Czech Republic functionality for fulfill dates, and the Polish functionality for the VAT register date include the requirement for tax information reporting that is based on a date that differs from the posting date.</span></span></p>
<p><span data-ttu-id="e358b-146">Il campo <strong>Data registro IVA</strong> supporta questo requisito e appare in più di 20 pagine.</span><span class="sxs-lookup"><span data-stu-id="e358b-146">The <strong>Date of VAT register</strong> field supports this requirement and appears on more than 20 pages.</span></span> <span data-ttu-id="e358b-147">Queste pagine includono giornali di registrazione, ordini cliente, ordini fornitore, fatture a testo libero, giornali di registrazione fatture fornitore e fatture di progetto.</span><span class="sxs-lookup"><span data-stu-id="e358b-147">These pages include journals, sales orders, purchase orders, free-text invoices, vendor invoice journals, and project invoices.</span></span> <span data-ttu-id="e358b-148">Quando si aggiornano o registrano i documenti, tutte le imposte vengono registrate con la data corrispondente del registro IVA e la data è inclusa nelle pagine quali le pagine dei giornali di registrazione fatture cliente e fornitore.</span><span class="sxs-lookup"><span data-stu-id="e358b-148">When you update or post the documents, all taxes are posted by using the corresponding date of the VAT register, and the date is included on pages such as the customer and vendor invoice journals pages.</span></span></p>
<p><span data-ttu-id="e358b-149">In particolare, per la Repubblica Ceca, il campo <strong>Data registro IVA</strong> può essere vuoto durante la registrazione, in caso di registrazione IVA posticipata.</span><span class="sxs-lookup"><span data-stu-id="e358b-149">Specifically, for the Czech Republic, the <strong>VAT register date</strong> field can be blank during posting, in the event of postponed VAT posting.</span></span> <span data-ttu-id="e358b-150">In caso contrario, il campo è obbligatorio e deve essere compilato.</span><span class="sxs-lookup"><span data-stu-id="e358b-150">Otherwise, the field is mandatory and must be filled in.</span></span></p>
<p><span data-ttu-id="e358b-151">I parametri di convalida della data possono essere impostati nella pagina <strong>Fasce IVA</strong>:</span><span class="sxs-lookup"><span data-stu-id="e358b-151">Date validation parameters can be set on the <strong>Sales tax groups</strong> page:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-152">I parametri <strong>Data di compilazione registro IVA</strong> e <strong>Compilazione data di vendita</strong> vengono utilizzati come metodo di compilazione predefinito per le date appropriate.</span><span class="sxs-lookup"><span data-stu-id="e358b-152">The <strong>Date of VAT register filling</strong> and <strong>Sales date filling</strong> parameters are used as a default filling method for appropriate dates.</span></span> <span data-ttu-id="e358b-153">Sono inoltre disponibili l'inserimento manuale e diversi metodi di immissione automatizzati.</span><span class="sxs-lookup"><span data-stu-id="e358b-153">Manual input and several automated input methods are also available.</span></span></li>
<li><span data-ttu-id="e358b-154">Il campo <strong>Data di vendita obbligatoria</strong> indica se la data di vendita deve essere inserita prima che venga registrata una fattura di vendita.</span><span class="sxs-lookup"><span data-stu-id="e358b-154">The <strong>Mandatory sales date</strong> field indicates whether the sales date must be entered before a sales invoice is posted.</span></span></li>
</ul>
<p><span data-ttu-id="e358b-155">Nella pagina <strong>Transazioni registro IVA</strong> è possibile inserire date vuote per il registro IVA per le transazioni fiscali registrate.</span><span class="sxs-lookup"><span data-stu-id="e358b-155">On the <strong>VAT Register transactions</strong> page, you can fill in blank dates for the VAT register for posted tax transactions.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="e358b-156">Date del registro IVA che includono l'imposta differita</span><span class="sxs-lookup"><span data-stu-id="e358b-156">VAT register dates that include deferred tax</span></span></td>
<td><span data-ttu-id="e358b-157">Ungheria</span><span class="sxs-lookup"><span data-stu-id="e358b-157">Hungary</span></span></td>
<td>
<p><span data-ttu-id="e358b-158">Le normative fiscali ungheresi richiedono che le fatture vengano create al momento dell'evasione o non oltre 15 giorni dopo l'evasione.</span><span class="sxs-lookup"><span data-stu-id="e358b-158">Hungary tax regulations require that invoices be created at either the time of fulfillment or no later than 15 days after fulfillment.</span></span></p>
<p><span data-ttu-id="e358b-159">La data di evasione è la data in cui sono stati forniti i servizi ordinati o la data in cui gli articoli ordinati sono stati consegnati.</span><span class="sxs-lookup"><span data-stu-id="e358b-159">The fulfillment date is either the date when the ordered services were provided or the date when ordered items were delivered.</span></span> <span data-ttu-id="e358b-160">Quando si aggiornano o si registrano i documenti, tutte le imposte vengono registrate utilizzando la data corrispondente del registro IVA e la data viene visualizzata nelle pagine pertinenti.</span><span class="sxs-lookup"><span data-stu-id="e358b-160">When you update or post the documents, all taxes are posted by using the corresponding date of the VAT register, and the date appears on relevant pages.</span></span> <span data-ttu-id="e358b-161">Inoltre, le normative richiedono che l'IVA sulla fornitura continua di servizi, quali affitto, leasing, consulenza e riscaldamento, soddisfi i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="e358b-161">Additionally, regulations require that VAT on continuous delivery of services, such as renting, leasing, consulting, and heating, meet the following criteria:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-162">L'IVA deve essere registrata in un conto di contabilità generale dedicato alla data della fattura.</span><span class="sxs-lookup"><span data-stu-id="e358b-162">VAT must be posted to a dedicated general ledger account on the invoice date.</span></span></li>
<li><span data-ttu-id="e358b-163">L'IVA deve essere trasferita dai conti speciali a un conto contabilità clienti IVA o a un conto fornitori e deve essere inclusa nella dichiarazione IVA alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="e358b-163">VAT must be transferred from the special accounts to a sales tax receivable account or a payable account, and must be included in the VAT report on the due date.</span></span></li>
</ul>
<p><span data-ttu-id="e358b-164">Per supportare questi requisiti, è possibile trasferire le registrazioni di contabilità generale al conto imposta differita in entrata e al conto imposta differita in uscita.</span><span class="sxs-lookup"><span data-stu-id="e358b-164">To support these requirements, you can transfer General ledger postings to the Deferred incoming tax account and the Deferred outgoing tax account.</span></span> <span data-ttu-id="e358b-165">Tuttavia, è necessario prima completare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="e358b-165">However, you must first complete the following prerequisites:</span></span></p>
<ul>
<li><span data-ttu-id="e358b-166">Impostare i conti contabilità clienti e fornitori IVA differita nei gruppi di registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="e358b-166">Set up the Deferred VAT Payable and Deferred VAT Receivable ledger accounts in ledger posting groups.</span></span></li>
<li><span data-ttu-id="e358b-167">Abilitare il parametro <strong>IVA differita</strong> per le fasce IVA articolo.</span><span class="sxs-lookup"><span data-stu-id="e358b-167">Enable the <strong>Deferred VAT</strong> parameter for item sales tax groups.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="e358b-168">Data IVA obbligatoria</span><span class="sxs-lookup"><span data-stu-id="e358b-168">Mandatory VAT date</span></span></td>
<td><span data-ttu-id="e358b-169">Polonia</span><span class="sxs-lookup"><span data-stu-id="e358b-169">Poland</span></span></td>
<td>
<p><span data-ttu-id="e358b-170">È possibile richiedere che la data del registro IVA sia inclusa nei record delle transazioni di acquisto e vendita.</span><span class="sxs-lookup"><span data-stu-id="e358b-170">You can require that the date of the VAT register be included in purchase and sales transaction records.</span></span> <span data-ttu-id="e358b-171">Pertanto, la data del registro IVA può essere acquisita prima della registrazione di una transazione.</span><span class="sxs-lookup"><span data-stu-id="e358b-171">Therefore, the date of the VAT register can be captured before a transaction is posted.</span></span> <span data-ttu-id="e358b-172">Questa funzionalità consente di evitare di dover gestire più transazioni alla fine del periodo.</span><span class="sxs-lookup"><span data-stu-id="e358b-172">This functionality helps you avoid having to handle multiple transactions at the end of the period.</span></span></p>
<p><span data-ttu-id="e358b-173">È possibile rendere il campo <strong>Data del registro IVA</strong> obbligatorio quando vengono registrate le transazioni cliente o fornitore.</span><span class="sxs-lookup"><span data-stu-id="e358b-173">You can make the <strong>Date of VAT register</strong> field mandatory when customer or vendor transactions are posted.</span></span> <span data-ttu-id="e358b-174">Per rendere obbligatorio questo campo, abilitare l'opzione <strong>Data IVA obbligatoria</strong> per il conto cliente o fornitore correlato.</span><span class="sxs-lookup"><span data-stu-id="e358b-174">To make this field mandatory, enable the <strong>VAT date is required</strong> option for the related customer or vendor account.</span></span></p>
</td>
</tr>
</tbody>
</table>
