---
title: Vincoli di tabella definiti dall'utente e dal sistema
description: "In questo articolo vengono descritti i due tipi di vincoli di tabella per i componenti di un modello di configurazione prodotto: definiti dall'utente e definiti dal sistema. I vincoli di tabella rappresentano le matrici delle combinazioni di attributo consentite, in cui ogni riga definisce un insieme di valori di attributi possibili."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c29adc87b9ef435b714a46ba1a96ef8226759b6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "314994"
---
# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="85791-104">Vincoli di tabella definiti dall'utente e dal sistema</span><span class="sxs-lookup"><span data-stu-id="85791-104">System-defined and user-defined table constraints</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85791-105">In questo articolo vengono descritti i due tipi di vincoli di tabella per i componenti di un modello di configurazione prodotto: definiti dall'utente e definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="85791-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="85791-106">I vincoli di tabella rappresentano le matrici delle combinazioni di attributo consentite, in cui ogni riga definisce un insieme di valori di attributi possibili.</span><span class="sxs-lookup"><span data-stu-id="85791-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="85791-107">I vincoli di tabella rappresentano matrici delle combinazioni di attributi consentite per i componenti in un modello di configurazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="85791-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="85791-108">Ogni riga nella tabella definisce un insieme di possibili valori degli attributi.</span><span class="sxs-lookup"><span data-stu-id="85791-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="85791-109">È possibile dichiarare due tipi di vincoli in un modello di configurazione prodotto:</span><span class="sxs-lookup"><span data-stu-id="85791-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="85791-110">**Vincolo espressione**: consente di creare un'espressione che definisca le relazioni tra gli attributi per garantire che durante la configurazione prodotto possano essere selezionati solo valori compatibili.</span><span class="sxs-lookup"><span data-stu-id="85791-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="85791-111">**Vincolo tabella**: consente di creare una tabella che definisca tutte le combinazioni consentite per un set di attributi specificato.</span><span class="sxs-lookup"><span data-stu-id="85791-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="85791-112">Sono disponibili due tipi di vincoli di tabella: vincoli di tabella definiti dall'utente e vincoli di tabella definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="85791-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="85791-113">In questo articolo vengono descritti i vincoli di tabella definiti dall'utente e dal sistema per i componenti di un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="85791-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="85791-114">Vincoli di tabella definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="85791-114">User-defined table constraints</span></span>
<span data-ttu-id="85791-115">Un vincolo di tabella definito dall'utente è un tipo di matrice utilizzato per descrivere le combinazioni di valori di attributo definiti in base ai tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="85791-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="85791-116">Ad esempio, se vengono prodotti altoparlanti, è possibile includere colonne per il rivestimento del cabinet e la griglia anteriore nel vincolo di tabella definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="85791-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="85791-117">Il tipo di attributo per il rivestimento del cabinet ha quattro valori e il tipo di attributo per la griglia anteriore ha tre valori.</span><span class="sxs-lookup"><span data-stu-id="85791-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="85791-118">Di conseguenza, se i vincoli non vengono utilizzati, sono possibili 4 × 3 = 12 combinazioni.</span><span class="sxs-lookup"><span data-stu-id="85791-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="85791-119">Tuttavia, in questo esempio sono consentite solo sei combinazioni, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="85791-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="85791-120">Queste informazioni vengono visualizzate nella scheda **Combinazioni consentite** della pagina **Modifica vincolo di tabella**.</span><span class="sxs-lookup"><span data-stu-id="85791-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="85791-121">Rivestimento del cabinet</span><span class="sxs-lookup"><span data-stu-id="85791-121">Cabinet finish</span></span> | <span data-ttu-id="85791-122">Griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="85791-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="85791-123">Nero</span><span class="sxs-lookup"><span data-stu-id="85791-123">Black</span></span>          | <span data-ttu-id="85791-124">Nero</span><span class="sxs-lookup"><span data-stu-id="85791-124">Black</span></span>       |
| <span data-ttu-id="85791-125">Nero</span><span class="sxs-lookup"><span data-stu-id="85791-125">Black</span></span>          | <span data-ttu-id="85791-126">Metallo</span><span class="sxs-lookup"><span data-stu-id="85791-126">Metal</span></span>       |
| <span data-ttu-id="85791-127">Quercia</span><span class="sxs-lookup"><span data-stu-id="85791-127">Oak</span></span>            | <span data-ttu-id="85791-128">Nero</span><span class="sxs-lookup"><span data-stu-id="85791-128">Black</span></span>       |
| <span data-ttu-id="85791-129">Palissandro</span><span class="sxs-lookup"><span data-stu-id="85791-129">Rosewood</span></span>       | <span data-ttu-id="85791-130">Bianco</span><span class="sxs-lookup"><span data-stu-id="85791-130">White</span></span>       |
| <span data-ttu-id="85791-131">Bianco</span><span class="sxs-lookup"><span data-stu-id="85791-131">White</span></span>          | <span data-ttu-id="85791-132">Nero</span><span class="sxs-lookup"><span data-stu-id="85791-132">Black</span></span>       |
| <span data-ttu-id="85791-133">Bianco</span><span class="sxs-lookup"><span data-stu-id="85791-133">White</span></span>          | <span data-ttu-id="85791-134">Bianco</span><span class="sxs-lookup"><span data-stu-id="85791-134">White</span></span>       |

<span data-ttu-id="85791-135">I vincoli di tabella definiti dall'utente vengono definiti dall'input di tabella statica che funziona nello stesso modo di un vincolo di espressione.</span><span class="sxs-lookup"><span data-stu-id="85791-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="85791-136">Quando si utilizza un vincolo di tabella definito dall'utente, il vantaggio consiste nel fatto che è spesso più semplice creare, comprendere e gestire tabelle rispetto a lunghi vincoli di espressione.</span><span class="sxs-lookup"><span data-stu-id="85791-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="85791-137">Vincoli di tabella definiti dal sistema</span><span class="sxs-lookup"><span data-stu-id="85791-137">System-defined table constraints</span></span>
<span data-ttu-id="85791-138">Un vincolo di tabella definito dal sistema crea un mapping dinamico tra un tipo di attributo e un campo in una tabella.</span><span class="sxs-lookup"><span data-stu-id="85791-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="85791-139">Quando un vincolo della tabella definito dal sistema viene incluso nel modello di configurazione prodotto, il mapping garantisce che anziché i valori del tipo di attributo vengano visualizzati i dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="85791-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="85791-140">Il risultato è un vincolo dinamico, poiché il contenuto della tabella può essere modificato (ad esempio, da altri moduli).</span><span class="sxs-lookup"><span data-stu-id="85791-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="85791-141">Quando si crea un vincolo di tabella definito dal sistema, si seleziona una tabella, è possibile scegliere la query da utilizzare e quindi si associano i tipi di attributo ai campi nella tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="85791-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="85791-142">I tipi di campi devono corrispondere ai tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="85791-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="85791-143">Prima che un vincolo di tabella possa essere reso effettivo in un modello di configurazione prodotto, deve essere incluso in un vincolo su uno dei componenti del modello.</span><span class="sxs-lookup"><span data-stu-id="85791-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="85791-144">La procedura è creare un nuovo vincolo, selezionare il tipo di vincolo di tabella e quindi selezionare la definizione di vincolo di tabella da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="85791-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="85791-145">Infine, tutti i campi del vincolo della tabella devono essere mappati agli attributi nel modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="85791-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="additional-resources"></a><span data-ttu-id="85791-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="85791-146">Additional resources</span></span>
--------

[<span data-ttu-id="85791-147">Concetti chiave nei modelli configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="85791-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)



