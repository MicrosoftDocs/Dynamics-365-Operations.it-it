---
title: Regole dei criteri di controllo
description: "È possibile utilizzare i criteri di controllo per valutare le note spese, le fatture fornitore e gli ordini fornitore per assicurare che siano conformi alle regole dei criteri create. Tutte le regole associate ai criteri di controllo vengono eseguite in modalità batch in base a una programmazione specificata.  Ciascuna regola dei criteri è un'istanza di un tipo di regola dei criteri. Può essere attiva solo una regola dei criteri per volta per ciascun tipo di regola dei criteri."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 04217e162090720d2a48c96aa9356cea2dbfa230
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="audit-policy-rules"></a><span data-ttu-id="9f141-106">Regole dei criteri di controllo</span><span class="sxs-lookup"><span data-stu-id="9f141-106">Audit policy rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9f141-107">È possibile utilizzare i criteri di controllo per valutare le note spese, le fatture fornitore e gli ordini fornitore per assicurare che siano conformi alle regole dei criteri create.</span><span class="sxs-lookup"><span data-stu-id="9f141-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="9f141-108">Tutte le regole associate ai criteri di controllo vengono eseguite in modalità batch in base a una programmazione specificata.</span><span class="sxs-lookup"><span data-stu-id="9f141-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="9f141-109">Ciascuna regola dei criteri è un'istanza di un tipo di regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="9f141-110">Può essere attiva solo una regola dei criteri per volta per ciascun tipo di regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="9f141-111">Query e tipi di query</span><span class="sxs-lookup"><span data-stu-id="9f141-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="9f141-112">Quando si crea una regola dei criteri di controllo, è necessario prima selezionare un tipo di regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="9f141-113">Il tipo di regola dei criteri consente di specificare la struttura a oggetti applicativi (AOT) da utilizzare come punto di partenza per la creazione della regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="9f141-114">Consente inoltre di specificare il tipo di query da utilizzare per la regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="9f141-115">La query determina il documento di origine che valuta la regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="9f141-116">Nella query vengono inoltre specificati i campi nel documento di origine che identificano la persona giuridica e la data da utilizzare quando i documenti vengono selezionati per il controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="9f141-117">Il tipo di query gestisce i campi predefiniti nella pagina di query e nella pagina Regola dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="9f141-118">Nella seguente tabella vengono visualizzati i tipi di query disponibili per le regole dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f141-119">Tipo di query</span><span class="sxs-lookup"><span data-stu-id="9f141-119">Query type</span></span></th>
<th><span data-ttu-id="9f141-120">Scopo</span><span class="sxs-lookup"><span data-stu-id="9f141-120">Purpose</span></span></th>
<th><span data-ttu-id="9f141-121">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9f141-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f141-122">Condizionale</span><span class="sxs-lookup"><span data-stu-id="9f141-122">Conditional</span></span></td>
<td><span data-ttu-id="9f141-123">Valutare gli attributi del documento di origine a fronte dei valori specificati.</span><span class="sxs-lookup"><span data-stu-id="9f141-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f141-124">Aggrega</span><span class="sxs-lookup"><span data-stu-id="9f141-124">Aggregate</span></span></td>
<td><span data-ttu-id="9f141-125">Valutare più documenti di origine o righe di documenti di origine a fronte di una regola dei criteri tramite l'aggregazione di valori numerici.</span><span class="sxs-lookup"><span data-stu-id="9f141-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f141-126">Campionamento</span><span class="sxs-lookup"><span data-stu-id="9f141-126">Sampling</span></span></td>
<td><span data-ttu-id="9f141-127">Effettuare la selezione casuale di una percentuale specificata dei documenti di origine da valutare a fronte delle violazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9f141-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="9f141-128">Quando si seleziona questa opzione, utilizzare la pagina Regola dei criteri di controllo per specificare la percentuale di documenti da selezionare in modo casuale per il controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f141-129">Duplicato</span><span class="sxs-lookup"><span data-stu-id="9f141-129">Duplicate</span></span></td>
<td><span data-ttu-id="9f141-130">Valutare i documenti di origine per determinare se contengono voci duplicate nei campi specificati.</span><span class="sxs-lookup"><span data-stu-id="9f141-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="9f141-131">Quando si seleziona questa opzione, utilizzare la pagina Regola dei criteri di controllo per specificare il numero di giorni da aggiungere all'inizio dell'intervallo date per la selezione dei documenti quando questi vengono valutati per la ricerca delle voci duplicate.</span><span class="sxs-lookup"><span data-stu-id="9f141-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f141-132">Elenca ricerca</span><span class="sxs-lookup"><span data-stu-id="9f141-132">List search</span></span></td>
<td><span data-ttu-id="9f141-133">Valutare i documenti di origine rispetto a entità specifiche.</span><span class="sxs-lookup"><span data-stu-id="9f141-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="9f141-134">Il documento principale della query definisce il documento in fase di controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="9f141-135">La query deve essere una query elenco contenente un riferimento alla tabella dirpartytable.</span><span class="sxs-lookup"><span data-stu-id="9f141-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="9f141-136">Questa opzione può essere utilizzata solo con le seguenti query AOT:</span><span class="sxs-lookup"><span data-stu-id="9f141-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="9f141-137"><span class="ui">AuditPolicyExpenseList</span> (dipendenti con nota spese controllata)</span><span class="sxs-lookup"><span data-stu-id="9f141-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="9f141-138"><span class="ui">AuditPolicyPurchList</span> (Fornitori con ordine acquisto controllato)</span><span class="sxs-lookup"><span data-stu-id="9f141-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="9f141-139"><span class="ui">AuditPolicyVendInvoiceList</span> (fornitori con fattura fornitore monitorata)</span><span class="sxs-lookup"><span data-stu-id="9f141-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="9f141-140">Quando si seleziona questa opzione, specificare le entità monitorate nella pagina Regola dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f141-141">Ricerca per parole chiave</span><span class="sxs-lookup"><span data-stu-id="9f141-141">Keyword search</span></span></td>
<td><span data-ttu-id="9f141-142">Valutare i documenti di origine per stabilire se contengono determinate parole.</span><span class="sxs-lookup"><span data-stu-id="9f141-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="9f141-143">Quando si seleziona questa opzione, immettere i termini da cercare nella pagina Regola dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="9f141-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="9f141-144">La pagina Regola dei criteri di controllo include opzioni che consentono di specificare le tabelle e i campi da valutare a fronte delle parole immesse.</span><span class="sxs-lookup"><span data-stu-id="9f141-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="9f141-145">Parametri comuni</span><span class="sxs-lookup"><span data-stu-id="9f141-145">Common parameters</span></span>
<span data-ttu-id="9f141-146">Tutte le regole dei criteri per determinati criteri di controllo condividono gli stessi parametri di batch e lo stesso intervallo date per selezione documenti.</span><span class="sxs-lookup"><span data-stu-id="9f141-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="9f141-147">Questi parametri sono specificati per i criteri nella pagina Opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="9f141-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="see-also"></a><span data-ttu-id="9f141-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f141-148">See also</span></span>
--------

<span data-ttu-id="9f141-149">[Casi e violazioni dei criteri di controllo](audit-policy-violations-cases.md)
[Definire i criteri di controllo per i documenti di origine](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="9f141-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>



