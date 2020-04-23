---
title: Vincoli di espressione e vincoli di tabella nei modelli di configurazione prodotto
description: In questo argomento viene descritto l'utilizzo dei vincoli di espressione e dei vincoli di tabella. I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione. È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d85d10113e7cc4e95a25efe7fee6d1f23990694
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208474"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="5967c-105">Vincoli di espressione e vincoli di tabella nei modelli di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="5967c-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5967c-106">In questo argomento viene descritto l'utilizzo dei vincoli di espressione e dei vincoli di tabella.</span><span class="sxs-lookup"><span data-stu-id="5967c-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="5967c-107">I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5967c-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="5967c-108">È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="5967c-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="5967c-109">I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5967c-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="5967c-110">È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="5967c-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="5967c-111">Cosa sono i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="5967c-111">What are expression constraints?</span></span>
<span data-ttu-id="5967c-112">I vincoli di espressione sono caratterizzati da un'espressione che utilizza funzioni e operatori aritmetici e booleani.</span><span class="sxs-lookup"><span data-stu-id="5967c-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="5967c-113">Un vincolo di espressione viene scritto per un componente specifico nel modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="5967c-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="5967c-114">e non può essere riutilizzato o condiviso con un altro componente.</span><span class="sxs-lookup"><span data-stu-id="5967c-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="5967c-115">Può tuttavia fare riferimento ad attributi di sottocomponenti del componente per cui è scritto.</span><span class="sxs-lookup"><span data-stu-id="5967c-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="5967c-116">Cosa sono i vincoli di tabella?</span><span class="sxs-lookup"><span data-stu-id="5967c-116">What are table constraints?</span></span>
<span data-ttu-id="5967c-117">I vincoli di tabella elencano le combinazioni di valori consentiti per gli attributi quando si configura un prodotto.</span><span class="sxs-lookup"><span data-stu-id="5967c-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="5967c-118">Le definizioni dei vincoli di tabella possono essere utilizzate genericamente.</span><span class="sxs-lookup"><span data-stu-id="5967c-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="5967c-119">Quando si crea un vincolo di tabella per un componente in un modello di configurazione prodotto, selezionare una definizione di vincolo di tabella.</span><span class="sxs-lookup"><span data-stu-id="5967c-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="5967c-120">Per creare le combinazioni consentite, si aggiungono attributi di tipi specifici ai componenti.</span><span class="sxs-lookup"><span data-stu-id="5967c-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="5967c-121">Ogni tipo di attributo ha un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="5967c-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="5967c-122">Esempio di vincolo di tabella</span><span class="sxs-lookup"><span data-stu-id="5967c-122">Example of a table constraint</span></span>

<span data-ttu-id="5967c-123">In questo esempio viene illustrato come è possibile limitare la configurazione di un altoparlante a rivestimenti e frontali specifici del cabinet.</span><span class="sxs-lookup"><span data-stu-id="5967c-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="5967c-124">Nella prima tabella vengono illustrati i rivestimenti e i frontali del cabinet che sono in genere disponibili per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5967c-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="5967c-125">I valori sono definiti per i tipi di attributo **Rivestimento del cabinet** e **Griglia anteriore**.</span><span class="sxs-lookup"><span data-stu-id="5967c-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="5967c-126">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="5967c-126">Attribute type</span></span> | <span data-ttu-id="5967c-127">Valori</span><span class="sxs-lookup"><span data-stu-id="5967c-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="5967c-128">Rivestimento del cabinet</span><span class="sxs-lookup"><span data-stu-id="5967c-128">Cabinet finish</span></span> | <span data-ttu-id="5967c-129">Nero, Quercia, Palissandro, Bianco</span><span class="sxs-lookup"><span data-stu-id="5967c-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="5967c-130">Griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="5967c-130">Front grill</span></span>    | <span data-ttu-id="5967c-131">Nero, Metallo, Bianco</span><span class="sxs-lookup"><span data-stu-id="5967c-131">Black, Metal, White</span></span>         |

<span data-ttu-id="5967c-132">Nella tabella seguente vengono illustrate le combinazioni definite dal vincolo di tabella **Colore e rivestimento**.</span><span class="sxs-lookup"><span data-stu-id="5967c-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="5967c-133">Utilizzando questo vincolo di tabella, è possibile configurare un altoparlante con un rivestimento di quercia e una griglia nera, un rivestimento di palissandro e una griglia bianca, ecc.</span><span class="sxs-lookup"><span data-stu-id="5967c-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="5967c-134">Fine</span><span class="sxs-lookup"><span data-stu-id="5967c-134">Finish</span></span>         | <span data-ttu-id="5967c-135">Griglia</span><span class="sxs-lookup"><span data-stu-id="5967c-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="5967c-136">Quercia</span><span class="sxs-lookup"><span data-stu-id="5967c-136">Oak</span></span>            | <span data-ttu-id="5967c-137">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-137">Black</span></span>                       |
| <span data-ttu-id="5967c-138">Palissandro</span><span class="sxs-lookup"><span data-stu-id="5967c-138">Rosewood</span></span>       | <span data-ttu-id="5967c-139">Bianco</span><span class="sxs-lookup"><span data-stu-id="5967c-139">White</span></span>                       |
| <span data-ttu-id="5967c-140">Bianco</span><span class="sxs-lookup"><span data-stu-id="5967c-140">White</span></span>          | <span data-ttu-id="5967c-141">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-141">Black</span></span>                       |
| <span data-ttu-id="5967c-142">Bianco</span><span class="sxs-lookup"><span data-stu-id="5967c-142">White</span></span>          | <span data-ttu-id="5967c-143">Bianco</span><span class="sxs-lookup"><span data-stu-id="5967c-143">White</span></span>                       |
| <span data-ttu-id="5967c-144">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-144">Black</span></span>          | <span data-ttu-id="5967c-145">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-145">Black</span></span>                       |
| <span data-ttu-id="5967c-146">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-146">Black</span></span>          | <span data-ttu-id="5967c-147">Metallo</span><span class="sxs-lookup"><span data-stu-id="5967c-147">Metal</span></span>                       | 

<span data-ttu-id="5967c-148">È possibile creare vincoli di tabella definiti dal sistema e vincoli di tabella definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5967c-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="5967c-149">Per ulteriori informazioni, vedere [Vincoli di tabella definiti dall'utente e dal sistema](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="5967c-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="5967c-150">Quale sintassi deve essere utilizzata per scrivere i vincoli?</span><span class="sxs-lookup"><span data-stu-id="5967c-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="5967c-151">Per scrivere i vincoli, è necessario utilizzare la sintassi OML (Optimization Modeling Language).</span><span class="sxs-lookup"><span data-stu-id="5967c-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="5967c-152">Il sistema utilizza il risolutore dei vincoli Microsoft Solver Foundation.</span><span class="sxs-lookup"><span data-stu-id="5967c-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="5967c-153">È meglio utilizzare i vincoli di tabella o i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="5967c-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="5967c-154">È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="5967c-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="5967c-155">Si sviluppa un vincolo di tabella come matrice, mentre un vincolo di espressione è una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="5967c-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="5967c-156">Quando si configura un prodotto, non importa il tipo di vincolo utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5967c-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="5967c-157">Nel seguente esempio è mostrato in che modo i due metodi differiscono.</span><span class="sxs-lookup"><span data-stu-id="5967c-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="5967c-158">Quando si configura un prodotto tramite le seguenti impostazioni del vincolo, sono consentite queste combinazioni:</span><span class="sxs-lookup"><span data-stu-id="5967c-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="5967c-159">Un prodotto di colore nero e con dimensioni 30 o 50</span><span class="sxs-lookup"><span data-stu-id="5967c-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="5967c-160">Un prodotto di colore rosso e con dimensioni 20</span><span class="sxs-lookup"><span data-stu-id="5967c-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="5967c-161">Impostazione del vincolo di tabella</span><span class="sxs-lookup"><span data-stu-id="5967c-161">Table constraint setup</span></span>

| <span data-ttu-id="5967c-162">Colore</span><span class="sxs-lookup"><span data-stu-id="5967c-162">Color</span></span> | <span data-ttu-id="5967c-163">Dimensione</span><span class="sxs-lookup"><span data-stu-id="5967c-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="5967c-164">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-164">Black</span></span> | <span data-ttu-id="5967c-165">30</span><span class="sxs-lookup"><span data-stu-id="5967c-165">30</span></span>   |
| <span data-ttu-id="5967c-166">Nero</span><span class="sxs-lookup"><span data-stu-id="5967c-166">Black</span></span> | <span data-ttu-id="5967c-167">50</span><span class="sxs-lookup"><span data-stu-id="5967c-167">50</span></span>   |
| <span data-ttu-id="5967c-168">Rosso</span><span class="sxs-lookup"><span data-stu-id="5967c-168">Red</span></span>   | <span data-ttu-id="5967c-169">20</span><span class="sxs-lookup"><span data-stu-id="5967c-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="5967c-170">Impostazione del vincolo di espressione</span><span class="sxs-lookup"><span data-stu-id="5967c-170">Expression constraint setup</span></span>

<span data-ttu-id="5967c-171">(Color == "Nero" & (size == "30" | size == "50")) | (color == "Rosso" & size = "20")</span><span class="sxs-lookup"><span data-stu-id="5967c-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="5967c-172">È necessario utilizzare gli operatori o la notazione di infisso quando si scrivono i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="5967c-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="5967c-173">È possibile scrivere un vincolo di espressione utilizzando gli operatori di prefisso disponibili o la notazione di infisso.</span><span class="sxs-lookup"><span data-stu-id="5967c-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="5967c-174">Per gli operatori **Min**, **Max** e **Abs** non è possibile utilizzare una notazione di infisso.</span><span class="sxs-lookup"><span data-stu-id="5967c-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="5967c-175">Questi operatori sono inclusi come operatori standard nella maggior parte dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="5967c-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="5967c-176">Quali operatori e notazione di infisso è possibile utilizzare quando si scrivono i vincoli di espressione?</span><span class="sxs-lookup"><span data-stu-id="5967c-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="5967c-177">Nelle tabelle seguenti sono elencati gli operatori e la notazione di infisso che è possibile utilizzare per scrivere un vincolo di espressione per un componente in un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="5967c-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="5967c-178">Negli esempi della prima tabella è possibile vedere come scrivere un'espressione utilizzando la notazione di infisso o gli operatori.</span><span class="sxs-lookup"><span data-stu-id="5967c-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5967c-179">Operatore</span><span class="sxs-lookup"><span data-stu-id="5967c-179">Operator</span></span></th>
<th><span data-ttu-id="5967c-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5967c-180">Description</span></span></th>
<th><span data-ttu-id="5967c-181">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5967c-181">Syntax</span></span></th>
<th><span data-ttu-id="5967c-182">Esempi</span><span class="sxs-lookup"><span data-stu-id="5967c-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5967c-183">Implies</span><span class="sxs-lookup"><span data-stu-id="5967c-183">Implies</span></span></td>
<td><span data-ttu-id="5967c-184">È true se la prima condizione è false, la seconda condizione è true o entrambi.</span><span class="sxs-lookup"><span data-stu-id="5967c-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="5967c-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="5967c-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-186"><strong>Operatore:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="5967c-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="5967c-187"><strong>Notazione di infisso:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="5967c-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5967c-188">E</span><span class="sxs-lookup"><span data-stu-id="5967c-188">And</span></span></td>
<td><span data-ttu-id="5967c-189">È true solo se tutte le condizioni sono true.</span><span class="sxs-lookup"><span data-stu-id="5967c-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="5967c-190">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>True</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="5967c-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="5967c-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-192"><strong>Operatore:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="5967c-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="5967c-193"><strong>Notazione di infisso:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="5967c-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5967c-194">O</span><span class="sxs-lookup"><span data-stu-id="5967c-194">Or</span></span></td>
<td><span data-ttu-id="5967c-195">È true se qualsiasi condizione è true.</span><span class="sxs-lookup"><span data-stu-id="5967c-195">This is true if any condition is true.</span></span> <span data-ttu-id="5967c-196">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="5967c-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="5967c-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-198"><strong>Operatore:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="5967c-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="5967c-199"><strong>Notazione di infisso:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="5967c-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5967c-200">Più</span><span class="sxs-lookup"><span data-stu-id="5967c-200">Plus</span></span></td>
<td><span data-ttu-id="5967c-201">Questa espressione somma le condizioni.</span><span class="sxs-lookup"><span data-stu-id="5967c-201">This sums its conditions.</span></span> <span data-ttu-id="5967c-202">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="5967c-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="5967c-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-204"><strong>Operatore:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="5967c-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="5967c-205"><strong>Notazione di infisso:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="5967c-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5967c-206">Meno</span><span class="sxs-lookup"><span data-stu-id="5967c-206">Minus</span></span></td>
<td><span data-ttu-id="5967c-207">Nega il proprio argomento.</span><span class="sxs-lookup"><span data-stu-id="5967c-207">This negates its argument.</span></span> <span data-ttu-id="5967c-208">Questa espressione deve avere esattamente una condizione.</span><span class="sxs-lookup"><span data-stu-id="5967c-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="5967c-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="5967c-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-210"><strong>Operatore:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="5967c-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="5967c-211"><strong>Notazione di infisso:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="5967c-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5967c-212">Abs</span><span class="sxs-lookup"><span data-stu-id="5967c-212">Abs</span></span></td>
<td><span data-ttu-id="5967c-213">Questa espressione accetta il valore assoluto della propria condizione.</span><span class="sxs-lookup"><span data-stu-id="5967c-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="5967c-214">Questa espressione deve avere esattamente una condizione.</span><span class="sxs-lookup"><span data-stu-id="5967c-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="5967c-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="5967c-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="5967c-216"><strong>Operatore:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="5967c-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5967c-217">Tempi</span><span class="sxs-lookup"><span data-stu-id="5967c-217">Times</span></span></td>
<td><span data-ttu-id="5967c-218">questa espressione accetta il prodotto delle proprie condizioni.</span><span class="sxs-lookup"><span data-stu-id="5967c-218">This takes the product of its conditions.</span></span> <span data-ttu-id="5967c-219">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="5967c-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="5967c-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-221"><strong>Operatore:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="5967c-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="5967c-222"><strong>Notazione di infisso:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="5967c-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5967c-223">Potenza</span><span class="sxs-lookup"><span data-stu-id="5967c-223">Power</span></span></td>
<td><span data-ttu-id="5967c-224">Questa espressione accetta un valore esponenziale.</span><span class="sxs-lookup"><span data-stu-id="5967c-224">This takes an exponential.</span></span> <span data-ttu-id="5967c-225">Questa espressione applica l'elevamento a potenza da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="5967c-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="5967c-226">Ciò significa che è associativa a destra e di conseguenza <strong>Power[a, b, c]</strong> equivale a <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="5967c-227"><strong>Elevamento a potenza</strong> può essere utilizzato solo se l'esponente è una costante positiva.</span><span class="sxs-lookup"><span data-stu-id="5967c-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="5967c-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="5967c-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-229"><strong>Operatore:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="5967c-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="5967c-230"><strong>Notazione di infisso:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="5967c-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5967c-231">Max.</span><span class="sxs-lookup"><span data-stu-id="5967c-231">Max</span></span></td>
<td><span data-ttu-id="5967c-232">Questa espressione genera la maggiore condizione.</span><span class="sxs-lookup"><span data-stu-id="5967c-232">This produces the largest condition.</span></span> <span data-ttu-id="5967c-233">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="5967c-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="5967c-234">Max[args]</span></span></td>
<td><span data-ttu-id="5967c-235"><strong>Operatore:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="5967c-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5967c-236">Min.</span><span class="sxs-lookup"><span data-stu-id="5967c-236">Min</span></span></td>
<td><span data-ttu-id="5967c-237">Questa espressione genera la condizione minore.</span><span class="sxs-lookup"><span data-stu-id="5967c-237">This produces the smallest condition.</span></span> <span data-ttu-id="5967c-238">Se il numero di condizioni è 0 (zero), viene generato il valore <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="5967c-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="5967c-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="5967c-239">Min[args]</span></span></td>
<td><span data-ttu-id="5967c-240"><strong>Operatore:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="5967c-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5967c-241">Non</span><span class="sxs-lookup"><span data-stu-id="5967c-241">Not</span></span></td>
<td><span data-ttu-id="5967c-242">Questa espressione genera l'inverso logico della propria condizione.</span><span class="sxs-lookup"><span data-stu-id="5967c-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="5967c-243">Questa espressione deve avere esattamente una condizione.</span><span class="sxs-lookup"><span data-stu-id="5967c-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="5967c-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="5967c-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="5967c-245"><strong>Operatore:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="5967c-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="5967c-246"><strong>Notazione di infisso:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="5967c-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5967c-247">Gli esempi nella seguente tabella illustrano come scrivere una notazione di infisso.</span><span class="sxs-lookup"><span data-stu-id="5967c-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="5967c-248">Notazione di infisso</span><span class="sxs-lookup"><span data-stu-id="5967c-248">Infix notation</span></span>   |                                          <span data-ttu-id="5967c-249">descrizione</span><span class="sxs-lookup"><span data-stu-id="5967c-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="5967c-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="5967c-250">x + y + z</span></span>     |                                           <span data-ttu-id="5967c-251">Addizione</span><span class="sxs-lookup"><span data-stu-id="5967c-251">Addition</span></span>                                            |
|    <span data-ttu-id="5967c-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="5967c-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="5967c-253">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="5967c-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="5967c-254">x - y</span><span class="sxs-lookup"><span data-stu-id="5967c-254">x - y</span></span>       | <span data-ttu-id="5967c-255">La sottrazione binaria è tradotta come l'addizione binaria nei casi in cui esiste un secondo valore negato.</span><span class="sxs-lookup"><span data-stu-id="5967c-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="5967c-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="5967c-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="5967c-257">Elevamento a potenza con associatività a destra</span><span class="sxs-lookup"><span data-stu-id="5967c-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="5967c-258">!x</span><span class="sxs-lookup"><span data-stu-id="5967c-258">!x</span></span>         |                                          <span data-ttu-id="5967c-259">Booleano not</span><span class="sxs-lookup"><span data-stu-id="5967c-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="5967c-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="5967c-260">x -: y</span></span>       |                                      <span data-ttu-id="5967c-261">Implicazione booleana</span><span class="sxs-lookup"><span data-stu-id="5967c-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="5967c-262">x</span><span class="sxs-lookup"><span data-stu-id="5967c-262">x</span></span>         |                                               <span data-ttu-id="5967c-263">y</span><span class="sxs-lookup"><span data-stu-id="5967c-263">y</span></span>                                               |
|     <span data-ttu-id="5967c-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="5967c-264">x & y & z</span></span>     |                                          <span data-ttu-id="5967c-265">Booleano and</span><span class="sxs-lookup"><span data-stu-id="5967c-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="5967c-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="5967c-266">x == y == z</span></span>    |                                           <span data-ttu-id="5967c-267">Uguaglianza</span><span class="sxs-lookup"><span data-stu-id="5967c-267">Equality</span></span>                                            |
|    <span data-ttu-id="5967c-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="5967c-268">x != y != z</span></span>    |                                           <span data-ttu-id="5967c-269">Distinto</span><span class="sxs-lookup"><span data-stu-id="5967c-269">Distinct</span></span>                                            |
|  <span data-ttu-id="5967c-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="5967c-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="5967c-271">Minore di</span><span class="sxs-lookup"><span data-stu-id="5967c-271">Less than</span></span>                                           |
|  <span data-ttu-id="5967c-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="5967c-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="5967c-273">Maggiore di</span><span class="sxs-lookup"><span data-stu-id="5967c-273">Greater than</span></span>                                          |
| <span data-ttu-id="5967c-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="5967c-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="5967c-275">Uguale o minore di</span><span class="sxs-lookup"><span data-stu-id="5967c-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="5967c-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="5967c-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="5967c-277">Uguale o maggiore di</span><span class="sxs-lookup"><span data-stu-id="5967c-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="5967c-278">(x)</span><span class="sxs-lookup"><span data-stu-id="5967c-278">(x)</span></span>        |                           <span data-ttu-id="5967c-279">Le parentesi hanno precedenza sulla priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="5967c-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="5967c-280">Perché i vincoli di espressione non vengono convalidati correttamente?</span><span class="sxs-lookup"><span data-stu-id="5967c-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="5967c-281">Non è possibile utilizzare le parole chiave riservate come nomi di risoluzione per gli attributi, i componenti o i sottocomponenti nel modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="5967c-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span><span data-ttu-id="5967c-282"> Ecco un elenco delle parole chiave riservate che non possono essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="5967c-282"> Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="5967c-283">Arrotonda eccesso</span><span class="sxs-lookup"><span data-stu-id="5967c-283">Ceiling</span></span>
-   <span data-ttu-id="5967c-284">Elemento</span><span class="sxs-lookup"><span data-stu-id="5967c-284">Element</span></span>
-   <span data-ttu-id="5967c-285">Uguale</span><span class="sxs-lookup"><span data-stu-id="5967c-285">Equal</span></span>
-   <span data-ttu-id="5967c-286">Piano</span><span class="sxs-lookup"><span data-stu-id="5967c-286">Floor</span></span>
-   <span data-ttu-id="5967c-287">Se</span><span class="sxs-lookup"><span data-stu-id="5967c-287">If</span></span>
-   <span data-ttu-id="5967c-288">Minore di</span><span class="sxs-lookup"><span data-stu-id="5967c-288">Less</span></span>
-   <span data-ttu-id="5967c-289">Maggiore di</span><span class="sxs-lookup"><span data-stu-id="5967c-289">Greater</span></span>
-   <span data-ttu-id="5967c-290">Implies</span><span class="sxs-lookup"><span data-stu-id="5967c-290">Implies</span></span>
-   <span data-ttu-id="5967c-291">Registro</span><span class="sxs-lookup"><span data-stu-id="5967c-291">Log</span></span>
-   <span data-ttu-id="5967c-292">Max.</span><span class="sxs-lookup"><span data-stu-id="5967c-292">Max</span></span>
-   <span data-ttu-id="5967c-293">Min.</span><span class="sxs-lookup"><span data-stu-id="5967c-293">Min</span></span>
-   <span data-ttu-id="5967c-294">Meno</span><span class="sxs-lookup"><span data-stu-id="5967c-294">Minus</span></span>
-   <span data-ttu-id="5967c-295">Più</span><span class="sxs-lookup"><span data-stu-id="5967c-295">Plus</span></span>
-   <span data-ttu-id="5967c-296">Potenza</span><span class="sxs-lookup"><span data-stu-id="5967c-296">Power</span></span>
-   <span data-ttu-id="5967c-297">Tempi</span><span class="sxs-lookup"><span data-stu-id="5967c-297">Times</span></span>
-   <span data-ttu-id="5967c-298">Fascia oraria</span><span class="sxs-lookup"><span data-stu-id="5967c-298">Slot</span></span>
-   <span data-ttu-id="5967c-299">Modello</span><span class="sxs-lookup"><span data-stu-id="5967c-299">Model</span></span>
-   <span data-ttu-id="5967c-300">Potere decisionale</span><span class="sxs-lookup"><span data-stu-id="5967c-300">Decision</span></span>
-   <span data-ttu-id="5967c-301">Obiettivo</span><span class="sxs-lookup"><span data-stu-id="5967c-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="5967c-302">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5967c-302">Additional resources</span></span>
--------

[<span data-ttu-id="5967c-303">Creare un vincolo di espressione</span><span class="sxs-lookup"><span data-stu-id="5967c-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="5967c-304">Aggiungere un calcolo a un modello di configurazione dei prodotti</span><span class="sxs-lookup"><span data-stu-id="5967c-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)



