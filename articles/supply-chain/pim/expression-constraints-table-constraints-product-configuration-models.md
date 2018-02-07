---
title: Vincoli di espressione e vincoli di tabella nei modelli di configurazione prodotto
description: "In questo argomento viene descritto l'utilizzo dei vincoli di espressione e dei vincoli di tabella. I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione. È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 3206e53c4f2659c6d9b9be64b01ac28cdd17bc88
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="907ae-105">Vincoli di espressione e vincoli di tabella nei modelli di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="907ae-105">Expression constraints and table constraints in product configuration models</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="907ae-106">In questo argomento viene descritto l'utilizzo dei vincoli di espressione e dei vincoli di tabella.</span><span class="sxs-lookup"><span data-stu-id="907ae-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="907ae-107">I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="907ae-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="907ae-108">È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="907ae-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="907ae-109">I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="907ae-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="907ae-110">È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="907ae-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="907ae-111">Cosa sono i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="907ae-111">What are expression constraints?</span></span>
<span data-ttu-id="907ae-112">I vincoli di espressione sono caratterizzati da un'espressione che utilizza funzioni e operatori aritmetici e booleani.</span><span class="sxs-lookup"><span data-stu-id="907ae-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="907ae-113">Un vincolo di espressione viene scritto per un componente specifico nel modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="907ae-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="907ae-114">e non può essere riutilizzato o condiviso con un altro componente.</span><span class="sxs-lookup"><span data-stu-id="907ae-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="907ae-115">Può tuttavia fare riferimento ad attributi di sottocomponenti del componente per cui è scritto.</span><span class="sxs-lookup"><span data-stu-id="907ae-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="907ae-116">Cosa sono i vincoli di tabella?</span><span class="sxs-lookup"><span data-stu-id="907ae-116">What are table constraints?</span></span>
<span data-ttu-id="907ae-117">I vincoli di tabella elencano le combinazioni di valori consentiti per gli attributi quando si configura un prodotto.</span><span class="sxs-lookup"><span data-stu-id="907ae-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="907ae-118">Le definizioni dei vincoli di tabella possono essere utilizzate genericamente.</span><span class="sxs-lookup"><span data-stu-id="907ae-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="907ae-119">Quando si crea un vincolo di tabella per un componente in un modello di configurazione prodotto, selezionare una definizione di vincolo di tabella.</span><span class="sxs-lookup"><span data-stu-id="907ae-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="907ae-120">Per creare le combinazioni consentite, si aggiungono attributi di tipi specifici ai componenti.</span><span class="sxs-lookup"><span data-stu-id="907ae-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="907ae-121">Ogni tipo di attributo ha un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="907ae-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="907ae-122">Esempio di vincolo di tabella</span><span class="sxs-lookup"><span data-stu-id="907ae-122">Example of a table constraint</span></span>

<span data-ttu-id="907ae-123">In questo esempio viene illustrato come è possibile limitare la configurazione di un altoparlante a rivestimenti e frontali specifici del cabinet.</span><span class="sxs-lookup"><span data-stu-id="907ae-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="907ae-124">Nella prima tabella vengono illustrati i rivestimenti e i frontali del cabinet che sono in genere disponibili per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="907ae-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="907ae-125">I valori sono definiti per i tipi di attributo **Rivestimento del cabinet** e **Griglia anteriore**.</span><span class="sxs-lookup"><span data-stu-id="907ae-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="907ae-126">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="907ae-126">Attribute type</span></span> | <span data-ttu-id="907ae-127">Valori</span><span class="sxs-lookup"><span data-stu-id="907ae-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="907ae-128">Rivestimento del cabinet</span><span class="sxs-lookup"><span data-stu-id="907ae-128">Cabinet finish</span></span> | <span data-ttu-id="907ae-129">Nero, Quercia, Palissandro, Bianco</span><span class="sxs-lookup"><span data-stu-id="907ae-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="907ae-130">Griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="907ae-130">Front grill</span></span>    | <span data-ttu-id="907ae-131">Nero, Metallo, Bianco</span><span class="sxs-lookup"><span data-stu-id="907ae-131">Black, Metal, White</span></span>         |

<span data-ttu-id="907ae-132">Nella tabella seguente vengono illustrate le combinazioni definite dal vincolo di tabella **Colore e rivestimento**.</span><span class="sxs-lookup"><span data-stu-id="907ae-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="907ae-133">Utilizzando questo vincolo di tabella, è possibile configurare un altoparlante con un rivestimento di quercia e una griglia nera, un rivestimento di palissandro e una griglia bianca, ecc.</span><span class="sxs-lookup"><span data-stu-id="907ae-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="907ae-134">Fine</span><span class="sxs-lookup"><span data-stu-id="907ae-134">Finish</span></span>         | <span data-ttu-id="907ae-135">Griglia</span><span class="sxs-lookup"><span data-stu-id="907ae-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="907ae-136">Quercia</span><span class="sxs-lookup"><span data-stu-id="907ae-136">Oak</span></span>            | <span data-ttu-id="907ae-137">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-137">Black</span></span>                       |
| <span data-ttu-id="907ae-138">Palissandro</span><span class="sxs-lookup"><span data-stu-id="907ae-138">Rosewood</span></span>       | <span data-ttu-id="907ae-139">Bianco</span><span class="sxs-lookup"><span data-stu-id="907ae-139">White</span></span>                       |
| <span data-ttu-id="907ae-140">Bianco</span><span class="sxs-lookup"><span data-stu-id="907ae-140">White</span></span>          | <span data-ttu-id="907ae-141">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-141">Black</span></span>                       |
| <span data-ttu-id="907ae-142">Bianco</span><span class="sxs-lookup"><span data-stu-id="907ae-142">White</span></span>          | <span data-ttu-id="907ae-143">Bianco</span><span class="sxs-lookup"><span data-stu-id="907ae-143">White</span></span>                       |
| <span data-ttu-id="907ae-144">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-144">Black</span></span>          | <span data-ttu-id="907ae-145">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-145">Black</span></span>                       |
| <span data-ttu-id="907ae-146">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-146">Black</span></span>          | <span data-ttu-id="907ae-147">Metallo</span><span class="sxs-lookup"><span data-stu-id="907ae-147">Metal</span></span>                       | 

<span data-ttu-id="907ae-148">È possibile creare vincoli di tabella definiti dal sistema e vincoli di tabella definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="907ae-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="907ae-149">Per ulteriori informazioni, vedere [Vincoli di tabella definiti dall'utente e dal sistema](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="907ae-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="907ae-150">Quale sintassi deve essere utilizzata per scrivere i vincoli?</span><span class="sxs-lookup"><span data-stu-id="907ae-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="907ae-151">Per scrivere i vincoli, è necessario utilizzare la sintassi OML (Optimization Modeling Language).</span><span class="sxs-lookup"><span data-stu-id="907ae-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="907ae-152">Il sistema utilizza il risolutore di vincoli Microsoft Solver Foundation per risolvere i vincoli.</span><span class="sxs-lookup"><span data-stu-id="907ae-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="907ae-153">È meglio utilizzare i vincoli di tabella o i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="907ae-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="907ae-154">È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="907ae-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="907ae-155">Si sviluppa un vincolo di tabella come matrice, mentre un vincolo di espressione è una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="907ae-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="907ae-156">Quando si configura un prodotto, non importa il tipo di vincolo utilizzato.</span><span class="sxs-lookup"><span data-stu-id="907ae-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="907ae-157">Nel seguente esempio è mostrato in che modo i due metodi differiscono.</span><span class="sxs-lookup"><span data-stu-id="907ae-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="907ae-158">Quando si configura un prodotto tramite le seguenti impostazioni del vincolo, sono consentite queste combinazioni:</span><span class="sxs-lookup"><span data-stu-id="907ae-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="907ae-159">Un prodotto di colore nero e con dimensioni 30 o 50</span><span class="sxs-lookup"><span data-stu-id="907ae-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="907ae-160">Un prodotto di colore rosso e con dimensioni 20</span><span class="sxs-lookup"><span data-stu-id="907ae-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="907ae-161">Impostazione del vincolo di tabella</span><span class="sxs-lookup"><span data-stu-id="907ae-161">Table constraint setup</span></span>

| <span data-ttu-id="907ae-162">Colore</span><span class="sxs-lookup"><span data-stu-id="907ae-162">Color</span></span> | <span data-ttu-id="907ae-163">Dimensione</span><span class="sxs-lookup"><span data-stu-id="907ae-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="907ae-164">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-164">Black</span></span> | <span data-ttu-id="907ae-165">30</span><span class="sxs-lookup"><span data-stu-id="907ae-165">30</span></span>   |
| <span data-ttu-id="907ae-166">Nero</span><span class="sxs-lookup"><span data-stu-id="907ae-166">Black</span></span> | <span data-ttu-id="907ae-167">50</span><span class="sxs-lookup"><span data-stu-id="907ae-167">50</span></span>   |
| <span data-ttu-id="907ae-168">Rosso</span><span class="sxs-lookup"><span data-stu-id="907ae-168">Red</span></span>   | <span data-ttu-id="907ae-169">20</span><span class="sxs-lookup"><span data-stu-id="907ae-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="907ae-170">Impostazione del vincolo di espressione</span><span class="sxs-lookup"><span data-stu-id="907ae-170">Expression constraint setup</span></span>

<span data-ttu-id="907ae-171">(Color == "Nero" & (size == "30" | size == "50")) | (color == "Rosso" & size = "20")</span><span class="sxs-lookup"><span data-stu-id="907ae-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="907ae-172">È necessario utilizzare gli operatori o la notazione di infisso quando si scrivono i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="907ae-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="907ae-173">È possibile scrivere un vincolo di espressione utilizzando gli operatori di prefisso disponibili o la notazione di infisso.</span><span class="sxs-lookup"><span data-stu-id="907ae-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="907ae-174">Per gli operatori **Min**, **Max** e **Abs** non è possibile utilizzare una notazione di infisso.</span><span class="sxs-lookup"><span data-stu-id="907ae-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="907ae-175">Questi operatori sono inclusi come operatori standard nella maggior parte dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="907ae-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="907ae-176">Quali operatori e notazione di infisso è possibile utilizzare quando si scrivono i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="907ae-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="907ae-177">Nelle tabelle seguenti sono elencati gli operatori e la notazione di infisso che è possibile utilizzare per scrivere un vincolo di espressione per un componente in un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="907ae-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="907ae-178">Negli esempi della prima tabella è possibile vedere come scrivere un'espressione utilizzando la notazione di infisso o gli operatori.</span><span class="sxs-lookup"><span data-stu-id="907ae-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="907ae-179">Operatore</span><span class="sxs-lookup"><span data-stu-id="907ae-179">Operator</span></span></th>
<th><span data-ttu-id="907ae-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="907ae-180">Description</span></span></th>
<th><span data-ttu-id="907ae-181">Sintassi</span><span class="sxs-lookup"><span data-stu-id="907ae-181">Syntax</span></span></th>
<th><span data-ttu-id="907ae-182">Esempi</span><span class="sxs-lookup"><span data-stu-id="907ae-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="907ae-183">Implies</span><span class="sxs-lookup"><span data-stu-id="907ae-183">Implies</span></span></td>
<td><span data-ttu-id="907ae-184">È true se la prima condizione è false, la seconda condizione è true o entrambi.</span><span class="sxs-lookup"><span data-stu-id="907ae-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="907ae-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="907ae-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-186"><strong>Operatore:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="907ae-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="907ae-187"><strong>Notazione di infisso:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="907ae-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="907ae-188">E</span><span class="sxs-lookup"><span data-stu-id="907ae-188">And</span></span></td>
<td><span data-ttu-id="907ae-189">È true solo se tutte le condizioni sono true.</span><span class="sxs-lookup"><span data-stu-id="907ae-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="907ae-190">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>True</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="907ae-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="907ae-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-192"><strong>Operatore:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="907ae-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="907ae-193"><strong>Notazione di infisso:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="907ae-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="907ae-194">O</span><span class="sxs-lookup"><span data-stu-id="907ae-194">Or</span></span></td>
<td><span data-ttu-id="907ae-195">È true se qualsiasi condizione è true.</span><span class="sxs-lookup"><span data-stu-id="907ae-195">This is true if any condition is true.</span></span> <span data-ttu-id="907ae-196">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="907ae-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="907ae-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-198"><strong>Operatore:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="907ae-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="907ae-199"><strong>Notazione di infisso:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="907ae-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="907ae-200">Più</span><span class="sxs-lookup"><span data-stu-id="907ae-200">Plus</span></span></td>
<td><span data-ttu-id="907ae-201">Questa espressione somma le condizioni.</span><span class="sxs-lookup"><span data-stu-id="907ae-201">This sums its conditions.</span></span> <span data-ttu-id="907ae-202">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="907ae-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="907ae-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-204"><strong>Operatore:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="907ae-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="907ae-205"><strong>Notazione di infisso:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="907ae-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="907ae-206">Meno</span><span class="sxs-lookup"><span data-stu-id="907ae-206">Minus</span></span></td>
<td><span data-ttu-id="907ae-207">Nega il proprio argomento.</span><span class="sxs-lookup"><span data-stu-id="907ae-207">This negates its argument.</span></span> <span data-ttu-id="907ae-208">Questa espressione deve avere esattamente una condizione.</span><span class="sxs-lookup"><span data-stu-id="907ae-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="907ae-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="907ae-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-210"><strong>Operatore:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="907ae-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="907ae-211"><strong>Notazione di infisso:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="907ae-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="907ae-212">Abs</span><span class="sxs-lookup"><span data-stu-id="907ae-212">Abs</span></span></td>
<td><span data-ttu-id="907ae-213">Questa espressione accetta il valore assoluto della propria condizione.</span><span class="sxs-lookup"><span data-stu-id="907ae-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="907ae-214">Questa espressione deve avere esattamente una condizione.</span><span class="sxs-lookup"><span data-stu-id="907ae-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="907ae-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="907ae-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="907ae-216"><strong>Operatore:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="907ae-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="907ae-217">Tempi</span><span class="sxs-lookup"><span data-stu-id="907ae-217">Times</span></span></td>
<td><span data-ttu-id="907ae-218">questa espressione accetta il prodotto delle proprie condizioni.</span><span class="sxs-lookup"><span data-stu-id="907ae-218">This takes the product of its conditions.</span></span> <span data-ttu-id="907ae-219">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="907ae-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="907ae-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-221"><strong>Operatore:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="907ae-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="907ae-222"><strong>Notazione di infisso:</strong> x * y * 2 == z</span><span class="sxs-lookup"><span data-stu-id="907ae-222"><strong>Infix notation:</strong> x * y * 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="907ae-223">Potenza</span><span class="sxs-lookup"><span data-stu-id="907ae-223">Power</span></span></td>
<td><span data-ttu-id="907ae-224">Questa espressione accetta un valore esponenziale.</span><span class="sxs-lookup"><span data-stu-id="907ae-224">This takes an exponential.</span></span> <span data-ttu-id="907ae-225">Questa espressione applica l'elevamento a potenza da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="907ae-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="907ae-226">Ciò significa che è associativa a destra e di conseguenza <strong>Power[a, b, c]</strong> equivale a <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-226">(In other words, it's right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="907ae-227"><strong>Elevamento a potenza</strong> può essere utilizzato solo se l'esponente è una costante positiva.</span><span class="sxs-lookup"><span data-stu-id="907ae-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="907ae-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="907ae-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-229"><strong>Operatore:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="907ae-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="907ae-230"><strong>Notazione di infisso:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="907ae-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="907ae-231">Max.</span><span class="sxs-lookup"><span data-stu-id="907ae-231">Max</span></span></td>
<td><span data-ttu-id="907ae-232">Questa espressione genera la maggiore condizione.</span><span class="sxs-lookup"><span data-stu-id="907ae-232">This produces the largest condition.</span></span> <span data-ttu-id="907ae-233">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="907ae-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="907ae-234">Max[args]</span></span></td>
<td><span data-ttu-id="907ae-235"><strong>Operatore:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="907ae-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="907ae-236">Min.</span><span class="sxs-lookup"><span data-stu-id="907ae-236">Min</span></span></td>
<td><span data-ttu-id="907ae-237">Questa espressione genera la condizione minore.</span><span class="sxs-lookup"><span data-stu-id="907ae-237">This produces the smallest condition.</span></span> <span data-ttu-id="907ae-238">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="907ae-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="907ae-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="907ae-239">Min[args]</span></span></td>
<td><span data-ttu-id="907ae-240"><strong>Operatore:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="907ae-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="907ae-241">Non</span><span class="sxs-lookup"><span data-stu-id="907ae-241">Not</span></span></td>
<td><span data-ttu-id="907ae-242">Questa espressione genera l'inverso logico della propria condizione.</span><span class="sxs-lookup"><span data-stu-id="907ae-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="907ae-243">Questa espressione deve avere esattamente una condizione.</span><span class="sxs-lookup"><span data-stu-id="907ae-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="907ae-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="907ae-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="907ae-245"><strong>Operatore:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="907ae-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="907ae-246"><strong>Notazione di infisso:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="907ae-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="907ae-247">Gli esempi nella seguente tabella illustrano come scrivere una notazione di infisso.</span><span class="sxs-lookup"><span data-stu-id="907ae-247">The examples in the next table show how to write infix notation.</span></span>

| <span data-ttu-id="907ae-248">Notazione di infisso</span><span class="sxs-lookup"><span data-stu-id="907ae-248">Infix notation</span></span>    | <span data-ttu-id="907ae-249">descrizione</span><span class="sxs-lookup"><span data-stu-id="907ae-249">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| <span data-ttu-id="907ae-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="907ae-250">x + y + z</span></span>         | <span data-ttu-id="907ae-251">Addizione</span><span class="sxs-lookup"><span data-stu-id="907ae-251">Addition</span></span>                                                                                      |
| <span data-ttu-id="907ae-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="907ae-252">x \* y \* z</span></span>       | <span data-ttu-id="907ae-253">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="907ae-253">Multiplication</span></span>                                                                                |
| <span data-ttu-id="907ae-254">x - y</span><span class="sxs-lookup"><span data-stu-id="907ae-254">x - y</span></span>             | <span data-ttu-id="907ae-255">La sottrazione binaria è tradotta come l'addizione binaria nei casi in cui esiste un secondo valore negato.</span><span class="sxs-lookup"><span data-stu-id="907ae-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
| <span data-ttu-id="907ae-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="907ae-256">x ^ y ^ z</span></span>         | <span data-ttu-id="907ae-257">Elevamento a potenza con associatività a destra</span><span class="sxs-lookup"><span data-stu-id="907ae-257">Exponentiation that has right associativity</span></span>                                                   |
| <span data-ttu-id="907ae-258">!x</span><span class="sxs-lookup"><span data-stu-id="907ae-258">!x</span></span>                | <span data-ttu-id="907ae-259">Booleano not</span><span class="sxs-lookup"><span data-stu-id="907ae-259">Boolean not</span></span>                                                                                   |
| <span data-ttu-id="907ae-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="907ae-260">x -: y</span></span>            | <span data-ttu-id="907ae-261">Implicazione booleana</span><span class="sxs-lookup"><span data-stu-id="907ae-261">Boolean implication</span></span>                                                                           |
| <span data-ttu-id="907ae-262"> interno </span><span class="sxs-lookup"><span data-stu-id="907ae-262">x</span></span> | <span data-ttu-id="907ae-263">y</span><span class="sxs-lookup"><span data-stu-id="907ae-263">y</span></span> | <span data-ttu-id="907ae-264">z</span><span class="sxs-lookup"><span data-stu-id="907ae-264">z</span></span>         | <span data-ttu-id="907ae-265">Booleano or</span><span class="sxs-lookup"><span data-stu-id="907ae-265">Boolean or</span></span>                                                                                    |
| <span data-ttu-id="907ae-266">x & y & z</span><span class="sxs-lookup"><span data-stu-id="907ae-266">x & y & z</span></span>         | <span data-ttu-id="907ae-267">Booleano and</span><span class="sxs-lookup"><span data-stu-id="907ae-267">Boolean and</span></span>                                                                                   |
| <span data-ttu-id="907ae-268">x == y == z</span><span class="sxs-lookup"><span data-stu-id="907ae-268">x == y == z</span></span>       | <span data-ttu-id="907ae-269">Uguaglianza</span><span class="sxs-lookup"><span data-stu-id="907ae-269">Equality</span></span>                                                                                      |
| <span data-ttu-id="907ae-270">x != y != z</span><span class="sxs-lookup"><span data-stu-id="907ae-270">x != y != z</span></span>       | <span data-ttu-id="907ae-271">Distinto</span><span class="sxs-lookup"><span data-stu-id="907ae-271">Distinct</span></span>                                                                                      |
| <span data-ttu-id="907ae-272">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="907ae-272">x &lt; y &lt; z</span></span>   | <span data-ttu-id="907ae-273">Minore di</span><span class="sxs-lookup"><span data-stu-id="907ae-273">Less than</span></span>                                                                                     |
| <span data-ttu-id="907ae-274">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="907ae-274">x &gt; y &gt; z</span></span>   | <span data-ttu-id="907ae-275">Maggiore di</span><span class="sxs-lookup"><span data-stu-id="907ae-275">Greater than</span></span>                                                                                  |
| <span data-ttu-id="907ae-276">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="907ae-276">x &lt;= y &lt;= z</span></span> | <span data-ttu-id="907ae-277">Uguale o minore di</span><span class="sxs-lookup"><span data-stu-id="907ae-277">Less than or equal to</span></span>                                                                         |
| <span data-ttu-id="907ae-278">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="907ae-278">x &gt;= y &gt;= z</span></span> | <span data-ttu-id="907ae-279">Uguale o maggiore di</span><span class="sxs-lookup"><span data-stu-id="907ae-279">Greater than or equal to</span></span>                                                                      |
| <span data-ttu-id="907ae-280">(x)</span><span class="sxs-lookup"><span data-stu-id="907ae-280">(x)</span></span>               | <span data-ttu-id="907ae-281">Le parentesi hanno precedenza sulla priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="907ae-281">Parentheses override default precedence.</span></span>                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="907ae-282">Perché i vincoli di espressione non vengono convalidati correttamente?</span><span class="sxs-lookup"><span data-stu-id="907ae-282">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="907ae-283">Non è possibile utilizzare le parole chiave riservate come nomi di risoluzione per gli attributi, i componenti o i sottocomponenti nel modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="907ae-283">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="907ae-284">Ecco un elenco delle parole chiave riservate che non possono essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="907ae-284">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="907ae-285">Arrotonda eccesso</span><span class="sxs-lookup"><span data-stu-id="907ae-285">Ceiling</span></span>
-   <span data-ttu-id="907ae-286">Elemento</span><span class="sxs-lookup"><span data-stu-id="907ae-286">Element</span></span>
-   <span data-ttu-id="907ae-287">Uguale</span><span class="sxs-lookup"><span data-stu-id="907ae-287">Equal</span></span>
-   <span data-ttu-id="907ae-288">Piano</span><span class="sxs-lookup"><span data-stu-id="907ae-288">Floor</span></span>
-   <span data-ttu-id="907ae-289">Se</span><span class="sxs-lookup"><span data-stu-id="907ae-289">If</span></span>
-   <span data-ttu-id="907ae-290">Minore di</span><span class="sxs-lookup"><span data-stu-id="907ae-290">Less</span></span>
-   <span data-ttu-id="907ae-291">Maggiore di</span><span class="sxs-lookup"><span data-stu-id="907ae-291">Greater</span></span>
-   <span data-ttu-id="907ae-292">Implies</span><span class="sxs-lookup"><span data-stu-id="907ae-292">Implies</span></span>
-   <span data-ttu-id="907ae-293">Registro</span><span class="sxs-lookup"><span data-stu-id="907ae-293">Log</span></span>
-   <span data-ttu-id="907ae-294">Max.</span><span class="sxs-lookup"><span data-stu-id="907ae-294">Max</span></span>
-   <span data-ttu-id="907ae-295">Min.</span><span class="sxs-lookup"><span data-stu-id="907ae-295">Min</span></span>
-   <span data-ttu-id="907ae-296">Meno</span><span class="sxs-lookup"><span data-stu-id="907ae-296">Minus</span></span>
-   <span data-ttu-id="907ae-297">Più</span><span class="sxs-lookup"><span data-stu-id="907ae-297">Plus</span></span>
-   <span data-ttu-id="907ae-298">Potenza</span><span class="sxs-lookup"><span data-stu-id="907ae-298">Power</span></span>
-   <span data-ttu-id="907ae-299">Tempi</span><span class="sxs-lookup"><span data-stu-id="907ae-299">Times</span></span>
-   <span data-ttu-id="907ae-300">Fascia oraria</span><span class="sxs-lookup"><span data-stu-id="907ae-300">Slot</span></span>
-   <span data-ttu-id="907ae-301">Modello</span><span class="sxs-lookup"><span data-stu-id="907ae-301">Model</span></span>
-   <span data-ttu-id="907ae-302">Potere decisionale</span><span class="sxs-lookup"><span data-stu-id="907ae-302">Decision</span></span>
-   <span data-ttu-id="907ae-303">Obiettivo</span><span class="sxs-lookup"><span data-stu-id="907ae-303">Goal</span></span>


<a name="see-also"></a><span data-ttu-id="907ae-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="907ae-304">See also</span></span>
--------

<span data-ttu-id="907ae-305">[Creare un vincolo di espressione (guida attività)(tasks/add-expression-constraint-product-configuration-model.md)</span><span class="sxs-lookup"><span data-stu-id="907ae-305">[Create an expression constraint (Task guide)(tasks/add-expression-constraint-product-configuration-model.md)</span></span>

[<span data-ttu-id="907ae-306">Aggiungere un calcolo a un modello di configurazione dei prodotti (guida attività)</span><span class="sxs-lookup"><span data-stu-id="907ae-306">Add a calculation to a product configuration model (Task guide)</span></span>](tasks/add-calculation-product-configuration-model.md)




