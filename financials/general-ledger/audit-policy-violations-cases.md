---
title: Casi e violazioni dei criteri di controllo
description: "L'articolo illustra come i casi di controllo vengono generati dalle violazioni delle regole dei criteri di controllo. Include inoltre le informazioni sulle varie modalità in cui i criteri di controllo utilizzano l'intervallo di date per la selezione dei documenti."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 24ee0dbf01208f8decc167e11e84191eaae03edf
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="audit-policy-violations-and-cases"></a><span data-ttu-id="a2854-104">Casi e violazioni dei criteri di controllo</span><span class="sxs-lookup"><span data-stu-id="a2854-104">Audit policy violations and cases</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a2854-105">L'articolo illustra come i casi di controllo vengono generati dalle violazioni delle regole dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="a2854-105">The article explains how audit cases are generated from violations of audit policy rules.</span></span> <span data-ttu-id="a2854-106">Include inoltre le informazioni sulle varie modalità in cui i criteri di controllo utilizzano l'intervallo di date per la selezione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a2854-106">It also includes information about the various ways that audit policies use the document selection date range.</span></span>

<a name="how-audit-cases-are-generated"></a><span data-ttu-id="a2854-107">Modalità di generazione dei casi di controllo</span><span class="sxs-lookup"><span data-stu-id="a2854-107">How audit cases are generated</span></span>
-----------------------------

<span data-ttu-id="a2854-108">I criteri di controllo vengono utilizzati per identificare note spese, ordini fornitore e fatture fornitore che non sono conformi alle regole di business definite e configurate come regole dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="a2854-108">Audit policies are used to identify expense reports, purchase orders, and vendor invoices that don't comply with business rules that you define and configure as audit policy rules.</span></span> 

<span data-ttu-id="a2854-109">I criteri di controllo vengono eseguiti in modalità batch.</span><span class="sxs-lookup"><span data-stu-id="a2854-109">Audit policies are run in batch mode.</span></span> <span data-ttu-id="a2854-110">Quando si eseguono dei criteri di controllo, tutte le regole dei criteri che rientrano in tali criteri vengono eseguite contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a2854-110">When you run an audit policy, all the policy rules that are part of that policy are run at the same time.</span></span>

<span data-ttu-id="a2854-111">Ogni regola dei criteri valuta un insieme di documenti.</span><span class="sxs-lookup"><span data-stu-id="a2854-111">Each policy rule evaluates a set of documents.</span></span> <span data-ttu-id="a2854-112">La regola dei criteri seleziona i documenti che sono inclusi nell'intervallo di date di selezione e che soddisfano i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="a2854-112">The policy rule selects documents that are in the document selection date range and that match the specified criteria.</span></span> <span data-ttu-id="a2854-113">Ad esempio, una regola dei criteri potrebbe selezionare le note spese con pasti di valore superiore a 50,00.</span><span class="sxs-lookup"><span data-stu-id="a2854-113">For example, one policy rule might select expense reports that have meals that exceed 50.00.</span></span> <span data-ttu-id="a2854-114">Un'altra regola dei criteri potrebbe selezionare le fatture fornitore a debito per un fornitore specifico.</span><span class="sxs-lookup"><span data-stu-id="a2854-114">Another policy rule might select vendor invoices that are payable to a specific vendor.</span></span> <span data-ttu-id="a2854-115">Per ogni documento selezionato nell'insieme, viene generata una violazione.</span><span class="sxs-lookup"><span data-stu-id="a2854-115">For each document that is selected in the set, a violation is generated.</span></span> <span data-ttu-id="a2854-116">Tale violazione è costituita da un record di un documento specifico, ad esempio la fattura 12345, che non è conforme alla regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="a2854-116">That violation is a record that a particular document, such as invoice 12345, doesn't comply with the policy rule.</span></span> 

<span data-ttu-id="a2854-117">Più record di violazione di controllo vengono raggruppati e associati ai casi di controllo.</span><span class="sxs-lookup"><span data-stu-id="a2854-117">Multiple audit violation records are grouped together and associated with audit cases.</span></span> <span data-ttu-id="a2854-118">Per impostazione predefinita, i casi relativi a ogni criterio di controllo vengono raggruppati per regola dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="a2854-118">By default, cases for each audit policy are grouped by audit policy rule.</span></span> <span data-ttu-id="a2854-119">Se si preferisce, è possibile selezionare altri criteri di raggruppamento tramite la pagina **Criteri di raggruppamento casi**.</span><span class="sxs-lookup"><span data-stu-id="a2854-119">If you prefer, you can select other grouping criteria by using the **Case grouping criteria** page.</span></span> <span data-ttu-id="a2854-120">È possibile, ad esempio, raggruppare le intestazioni di spesa per ID progetto e le fatture fornitore per conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="a2854-120">For example, you can group expense headers by project ID and vendor invoices by vendor account.</span></span> <span data-ttu-id="a2854-121">In tal caso, tutte le violazioni alle intestazioni di spesa con lo stesso ID progetto e tutte le fatture fornitore con lo stesso conto fornitore verranno raggruppate, rispettivamente, nello stesso caso.</span><span class="sxs-lookup"><span data-stu-id="a2854-121">In this case, all expense header violations that have the same project ID will be grouped in the same case, and all vendor invoices that have the same vendor account will be grouped in the same case.</span></span> 

> [!NOTE]
> <span data-ttu-id="a2854-122">Per le regole dei criteri di controllo basate su un tipo di query **Duplicato**, le violazioni non vengono raggruppate in base alla regola dei criteri di controllo o in base ai criteri specificati nella pagina **Criteri di raggruppamento casi**.</span><span class="sxs-lookup"><span data-stu-id="a2854-122">For audit policy rules that are based on a **Duplicate** query type, violations aren't grouped by policy rule or by the criteria that are specified on the **Case grouping criteria** page.</span></span> <span data-ttu-id="a2854-123">ma verranno invece raggruppate in base ai criteri incorporati nella regola dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="a2854-123">Instead, they are grouped by the criteria that are built into the audit policy rule.</span></span> <span data-ttu-id="a2854-124">Ad esempio, se una regola dei criteri valuta le note spese in base alle spese duplicate con uguale importo, ID esercente e data, tutte le spese con gli stessi valori in questi campi rappresenteranno un caso.</span><span class="sxs-lookup"><span data-stu-id="a2854-124">For example, if a policy rule evaluates expense reports for duplicate expenses of the same amount, merchant ID, and date, all expenses that have the same values in those fields will be one case.</span></span> <span data-ttu-id="a2854-125">Qualsiasi spesa con valori diversi rappresenterà un caso distinto.</span><span class="sxs-lookup"><span data-stu-id="a2854-125">Any expenses that have different values will be a separate case.</span></span>

<span data-ttu-id="a2854-126">Dopo la generazione, i casi di controllo verranno gestiti mediante i tipici processi di gestione dei casi.</span><span class="sxs-lookup"><span data-stu-id="a2854-126">After the audit cases have been generated, they are handled by using the typical processes for case management.</span></span>

## <a name="document-selection-date-ranges"></a><span data-ttu-id="a2854-127">Intervalli di date per la selezione di documenti</span><span class="sxs-lookup"><span data-stu-id="a2854-127">Document selection date ranges</span></span>
<span data-ttu-id="a2854-128">Quando si esegue un criterio di controllo, ogni regola dei criteri seleziona documenti del tipo specificato con data inclusa nell'intervallo di date per la selezione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a2854-128">When an audit policy is run, each policy rule selects documents of the specified type that have a date that is in the document selection date range.</span></span> <span data-ttu-id="a2854-129">L'intervallo delle date di selezione di documenti viene specificato nella pagina **Opzioni aggiuntive**.</span><span class="sxs-lookup"><span data-stu-id="a2854-129">The document selection date range is specified on the **Additional options** page.</span></span> <span data-ttu-id="a2854-130">A molti documenti è associata più di una data.</span><span class="sxs-lookup"><span data-stu-id="a2854-130">Many documents have more than one date associated with them.</span></span> <span data-ttu-id="a2854-131">Il campo date utilizzato dalla regola dei criteri di controllo è specificato nella pagina **Tipo di regola dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="a2854-131">The date field that the audit policy rule uses is specified on the **Policy rule type** page.</span></span>

<span data-ttu-id="a2854-132">Di seguito sono riportate altre modalità in cui un criterio di controllo utilizza l'intervallo di date per selezione documenti:</span><span class="sxs-lookup"><span data-stu-id="a2854-132">Here are some other ways that an audit policy uses the document selection date range:</span></span>

-   <span data-ttu-id="a2854-133">I criteri utilizzano la versione di ogni regola dei criteri che risulta valida nell'ultimo giorno dell'intervallo delle date per la selezione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a2854-133">The policy uses the version of each policy rule that is effective on the last day of the document selection date range.</span></span> <span data-ttu-id="a2854-134">È possibile visualizzare le date di validità di ogni regola dei criteri nella pagina elenco **Criteri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="a2854-134">You can view the effective dates for each policy rule on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="a2854-135">I criteri utilizzano i nodi dell'organizzazione che risultano associati ai criteri nell'ultimo giorno dell'intervallo delle date per la selezione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a2854-135">The policy uses the organization nodes that are associated with the policy on the last day of the document selection date range.</span></span> <span data-ttu-id="a2854-136">Solo i nodi dell'organizzazione attualmente associati ai criteri vengono visualizzati nella pagina elenco **Criteri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="a2854-136">Only the organization nodes that are currently associated with the policy appear on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="a2854-137">Per le regole dei criteri che si basano su un tipo di query **Elenca ricerca**, i criteri valutano documenti per le entità controllate che risultano valide nell'ultimo giorno dell'intervallo delle date per la selezione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a2854-137">For policy rules that are based on a **List search** query type, the policy evaluates documents for monitored entities that are effective on the last day of the document selection date range.</span></span>


<span data-ttu-id="a2854-138">Per ulteriori informazioni, vedere [Regole dei criteri di controllo](audit-policy-rules.md)</span><span class="sxs-lookup"><span data-stu-id="a2854-138">For more information, see [Audit policy rules](audit-policy-rules.md)</span></span>




