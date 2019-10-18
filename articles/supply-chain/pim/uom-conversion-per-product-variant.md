---
title: Conversione di unità per varianti prodotto
description: In questo argomento viene descritto come impostare conversioni di unità per varianti prodotto.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 196b68db02867f8d864be8bcc593aa01f554f7c3
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249450"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="82372-103">Conversione di unità per varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

<span data-ttu-id="82372-104">In questo argomento viene descritto come impostare conversioni di unità per varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="82372-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="82372-105">Include un esempio dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="82372-105">It includes an example of the setup.</span></span>

<span data-ttu-id="82372-106">Questa funzionalità consente alle società di definire differenti conversioni di unità tra le varianti dello stesso prodotto.</span><span class="sxs-lookup"><span data-stu-id="82372-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="82372-107">In questo argomento viene utilizzato l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="82372-107">The following example is used in this topic.</span></span> <span data-ttu-id="82372-108">Una società vende magliette nelle taglie S, M, L e XL.</span><span class="sxs-lookup"><span data-stu-id="82372-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="82372-109">La maglietta è definita come prodotto e le diverse taglie sono definite come varianti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="82372-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="82372-110">Le magliette sono imballate in scatole e ogni scatola può contenere cinque magliette S, M o L e quattro magliette XL.</span><span class="sxs-lookup"><span data-stu-id="82372-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="82372-111">La società desidera tenere traccia delle differenti varianti di magliette nell'unità **Pezzi** ma vende le magliette nell'unità **Scatole**.</span><span class="sxs-lookup"><span data-stu-id="82372-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="82372-112">La conversione tra l'unità di magazzino e l'unità di vendita è 1 scatola = 5 pezzi, ad eccezione della variante XL, dove la conversione è 1 scatola = 4 pezzi.</span><span class="sxs-lookup"><span data-stu-id="82372-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

## <a name="setup"></a><span data-ttu-id="82372-113">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="82372-113">Setup</span></span>

<span data-ttu-id="82372-114">È possibile configurare i parametri per l'utilizzo della funzionalità con prodotti abilitati per **Tutti i processi** o solo con il prodotto abilitato per **Processi di magazzino** utilizzando l'opzione **Abilita conversioni di unità di misura** nella pagina **Parametri informazioni sul prodotto**.</span><span class="sxs-lookup"><span data-stu-id="82372-114">You can configure the parameters for using the feature for products enabled for **All processes** or only for product enabled for the **Warehouse processes** by using the **Enable unit of measure conversations** option on the **Product information parameters** page.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="82372-115">Configurare un prodotto per la conversione di unità per variante</span><span class="sxs-lookup"><span data-stu-id="82372-115">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="82372-116">Le varianti prodotto possono essere create solo per prodotti di **Sottotipo di prodotto**: **Rappresentazione generale prodotto**.</span><span class="sxs-lookup"><span data-stu-id="82372-116">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="82372-117">Per ulteriori informazioni, vedere [Creare una rappresentazione generale prodotto](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="82372-117">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="82372-118">La funzionalità non è attivata per i prodotti configurati per i processi a peso variabile.</span><span class="sxs-lookup"><span data-stu-id="82372-118">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="82372-119">Durante la creazione di una rappresentazione generale prodotto abilitare la conversione di unità utilizzando l'opzione **Abilita conversioni di unità di misura** nella pagina **Dettagli prodotto**.</span><span class="sxs-lookup"><span data-stu-id="82372-119">During the creation of a product master enable unit of measure conversion by using the **Enable unit of measure conversions** option on the **Product details** page.</span></span>

<span data-ttu-id="82372-120">Quando viene creata la rappresentazione generale prodotto con varianti prodotto rilasciato, è possibile impostare conversioni di unità per varianti.</span><span class="sxs-lookup"><span data-stu-id="82372-120">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="82372-121">È possibile trovare la voce di menu per l'apertura della pagina delle conversione di unità nel contesto di un prodotto o di una variante prodotto nelle pagine seguenti.</span><span class="sxs-lookup"><span data-stu-id="82372-121">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="82372-122">Pagina **Dettagli prodotto**</span><span class="sxs-lookup"><span data-stu-id="82372-122">**Product details** page</span></span>
-   <span data-ttu-id="82372-123">Pagina **Dettagli prodotti rilasciati**</span><span class="sxs-lookup"><span data-stu-id="82372-123">**Released products details** page</span></span>
-   <span data-ttu-id="82372-124">Pagina **Varianti prodotti rilasciati**</span><span class="sxs-lookup"><span data-stu-id="82372-124">**Released product variants** page</span></span>

<span data-ttu-id="82372-125">Quando si apre la pagina **Conversione unità** nel contesto di una rappresentazione generale prodotto o di una variante prodotto rilasciato, è possibile selezionare se si desidera impostare la conversione di unità per il prodotto o per una variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="82372-125">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="82372-126">A questo proposito, selezionare **Variante prodotto** o **Prodotto** nel campo **Creare conversione per**.</span><span class="sxs-lookup"><span data-stu-id="82372-126">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="82372-127">Variante prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-127">Product variant</span></span>

<span data-ttu-id="82372-128">Se si seleziona **Variante prodotto**, è possibile selezionare la variante per la quale si desidera impostare la conversione di unità nel campo **Variante prodotto**.</span><span class="sxs-lookup"><span data-stu-id="82372-128">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="82372-129">Prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-129">Product</span></span>

<span data-ttu-id="82372-130">Se si seleziona **Prodotto**, è possibile impostare una conversione di unità per la rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="82372-130">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="82372-131">Questa conversione di unità verrà applicata per tutte le varianti prodotto senza conversione di unità definita.</span><span class="sxs-lookup"><span data-stu-id="82372-131">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="82372-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="82372-132">Example</span></span>

<span data-ttu-id="82372-133">Una rappresentazione generale prodotto, **Maglietta**, include quattro varianti prodotto rilasciato: S, M, L e XL.</span><span class="sxs-lookup"><span data-stu-id="82372-133">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="82372-134">Le magliette sono imballate in scatole e ogni scatola può contenere cinque magliette S, M o L e quattro magliette XL.</span><span class="sxs-lookup"><span data-stu-id="82372-134">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="82372-135">Innanzitutto, aprire la pagina **Conversione unità** dalla pagina Dettagli prodotto rilasciato per **Maglietta**.</span><span class="sxs-lookup"><span data-stu-id="82372-135">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="82372-136">Nella pagina **Conversione unità**, impostare la conversione di unità per la variante prodotto rilasciato XL.</span><span class="sxs-lookup"><span data-stu-id="82372-136">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="82372-137">**Campo**</span><span class="sxs-lookup"><span data-stu-id="82372-137">**Field**</span></span>             | <span data-ttu-id="82372-138">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="82372-138">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="82372-139">Crea conversione per</span><span class="sxs-lookup"><span data-stu-id="82372-139">Create conversion for</span></span> | <span data-ttu-id="82372-140">Variante prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-140">Product variant</span></span>         |
| <span data-ttu-id="82372-141">Variante prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-141">Product variant</span></span>       | <span data-ttu-id="82372-142">Maglietta : : XL : :</span><span class="sxs-lookup"><span data-stu-id="82372-142">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="82372-143">Dall'unità</span><span class="sxs-lookup"><span data-stu-id="82372-143">From unit</span></span>             | <span data-ttu-id="82372-144">Scatole</span><span class="sxs-lookup"><span data-stu-id="82372-144">Boxes</span></span>                   |
| <span data-ttu-id="82372-145">Fattore</span><span class="sxs-lookup"><span data-stu-id="82372-145">Factor</span></span>                | <span data-ttu-id="82372-146">4</span><span class="sxs-lookup"><span data-stu-id="82372-146">4</span></span>                       |
| <span data-ttu-id="82372-147">All'unità</span><span class="sxs-lookup"><span data-stu-id="82372-147">To Unit</span></span>               | <span data-ttu-id="82372-148">Pezzi</span><span class="sxs-lookup"><span data-stu-id="82372-148">Pieces</span></span>                  |

<span data-ttu-id="82372-149">Le varianti prodotto rilasciato S, M e L hanno la stessa conversione di unità tra l'unità Scatola e Pezzi, a significare che è possibile definire la conversione di unità per queste varianti prodotto nella rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="82372-149">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="82372-150">**Campo**</span><span class="sxs-lookup"><span data-stu-id="82372-150">**Field**</span></span>             | <span data-ttu-id="82372-151">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="82372-151">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="82372-152">Crea conversione per</span><span class="sxs-lookup"><span data-stu-id="82372-152">Create conversion for</span></span> | <span data-ttu-id="82372-153">Prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-153">Product</span></span>     |
| <span data-ttu-id="82372-154">Prodotto</span><span class="sxs-lookup"><span data-stu-id="82372-154">Product</span></span>               | <span data-ttu-id="82372-155">Maglietta</span><span class="sxs-lookup"><span data-stu-id="82372-155">T-Shirt</span></span>     |
| <span data-ttu-id="82372-156">Dall'unità</span><span class="sxs-lookup"><span data-stu-id="82372-156">From unit</span></span>             | <span data-ttu-id="82372-157">Scatole</span><span class="sxs-lookup"><span data-stu-id="82372-157">Boxes</span></span>       |
| <span data-ttu-id="82372-158">Fattore</span><span class="sxs-lookup"><span data-stu-id="82372-158">Factor</span></span>                | <span data-ttu-id="82372-159">5</span><span class="sxs-lookup"><span data-stu-id="82372-159">5</span></span>           |
| <span data-ttu-id="82372-160">All'unità</span><span class="sxs-lookup"><span data-stu-id="82372-160">To Unit</span></span>               | <span data-ttu-id="82372-161">Pezzi</span><span class="sxs-lookup"><span data-stu-id="82372-161">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="82372-162">Utilizzo di Excel per aggiornare le conversioni di unità</span><span class="sxs-lookup"><span data-stu-id="82372-162">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="82372-163">Se un prodotto include molte varianti prodotto con differenti conversioni di unità, è consigliabile esportare le conversioni di unità dalla pagina **Conversione unità** in un foglio di calcolo di Excel, aggiornare le conversioni e quindi pubblicarle di nuovo in Supply Chain Mangement.</span><span class="sxs-lookup"><span data-stu-id="82372-163">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="82372-164">L'opzione per esportare in Excel e pubblicare di nuovo le modifiche in Supply Chain Mangement viene abilitata mediante la voce di menu **Apri in Microsoft office** nel riquadro azioni della pagina **Conversione unità**.</span><span class="sxs-lookup"><span data-stu-id="82372-164">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
