---
title: Conversione di unità di misura per varianti prodotto
description: In questo argomento viene descritto come configurare conversioni di unità di misura per varianti prodotto. Include un esempio dell'impostazione.
author: johanhoffmann
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 71d35d47a703f0931ba3b4ab5df21c7199c7ea5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431436"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="426fa-104">Conversione di unità di misura per varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="426fa-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="426fa-105">In questo argomento viene descritto come configurare conversioni di unità di misura per diverse varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="426fa-106">Anziché creare più dispositivi individuali che devono essere mantenuti, puoi utilizzare le varianti dei prodotti per creare variazioni di un singolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="426fa-107">Ad esempio, una variante prodotto potrebbe essere una maglietta di una determinata taglia e colore.</span><span class="sxs-lookup"><span data-stu-id="426fa-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="426fa-108">In precedenza, le conversioni delle unità potevano essere impostate solo sulla rappresentazione generale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="426fa-109">Pertanto, tutte le varianti del prodotto avevano le stesse regole di conversione dell'unità.</span><span class="sxs-lookup"><span data-stu-id="426fa-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="426fa-110">Tuttavia, quando la funzionalità *Conversioni unità di misura per varianti prodotto* è attivata, se le magliette sono vendute in scatole e il numero di magliette che possono essere imballate in una scatola dipende dalle dimensioni delle magliette, ora è possibile impostare conversioni di unità tra le diverse dimensioni delle magliette e le scatole utilizzate per l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="426fa-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="426fa-111">Attiva la funzionalità nel tuo sistema</span><span class="sxs-lookup"><span data-stu-id="426fa-111">Turn on the feature in your system</span></span>

<span data-ttu-id="426fa-112">Se non vedi già questa funzione nel tuo sistema, vai a [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e abilita la funzionalità *Conversioni unità di misura per varianti prodotto*.</span><span class="sxs-lookup"><span data-stu-id="426fa-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="426fa-113">Configurare un prodotto per la conversione di unità per variante</span><span class="sxs-lookup"><span data-stu-id="426fa-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="426fa-114">Le varianti prodotto possono essere create solo per i prodotti che sono rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="426fa-115">Per ulteriori informazioni, vedere [Creare una rappresentazione generale prodotto](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="426fa-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="426fa-116">La funzionalità *Conversioni unità di misura per varianti prodotto* non è disponibile per i prodotti impostati per processi di peso variabile.</span><span class="sxs-lookup"><span data-stu-id="426fa-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="426fa-117">Per configurare una rappresentazione generale prodotto per supportare la conversione di unità per variante, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="426fa-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="426fa-118">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**.</span><span class="sxs-lookup"><span data-stu-id="426fa-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="426fa-119">Crea o apri una rappresentazione generale prodotto per andare alla sua pagina **Dettagli prodotto**.</span><span class="sxs-lookup"><span data-stu-id="426fa-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="426fa-120">Imposta l'opzione **Abilita conversioni unità di misura** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="426fa-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="426fa-121">Nel riquadro azioni, scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Conversioni unità**.</span><span class="sxs-lookup"><span data-stu-id="426fa-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="426fa-122">Viene aperta la pagina **Conversioni unità**.</span><span class="sxs-lookup"><span data-stu-id="426fa-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="426fa-123">Selezionare una delle schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="426fa-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="426fa-124">**Conversioni in classi**: seleziona questa scheda per convertire le unità appartenenti alla stessa classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="426fa-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="426fa-125">**Conversioni tra classi**: seleziona questa scheda per convertire le unità appartenenti a classi di unità di misura differenti.</span><span class="sxs-lookup"><span data-stu-id="426fa-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="426fa-126">Seleziona **Nuovo** per aggiungere una nuova conversione unità.</span><span class="sxs-lookup"><span data-stu-id="426fa-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="426fa-127">Imposta il campo **Crea conversione per** su uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="426fa-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="426fa-128">**Prodotto**: se selezioni questo valore puoi configurare una conversione unità per la rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="426fa-129">Questa conversione di unità verrà utilizzata come fallback per tutte le varianti di prodotto per le quali non è definita alcuna conversione di unità.</span><span class="sxs-lookup"><span data-stu-id="426fa-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="426fa-130">**Variante prodotto**: se selezioni questo valore puoi configurare una conversione unità per una specifica variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="426fa-131">Usa il campo **Variante prodotto** per selezionare la variante.</span><span class="sxs-lookup"><span data-stu-id="426fa-131">Use the **Product variant** field to select the variant.</span></span>

    ![![Aggiunta di una nuova conversione unità](media/uom-new-conversion.png "Aggiunta di una nuova conversione unità")](media/uom-new-conversion.png "Adding a new unit conversion")

1. <span data-ttu-id="426fa-133">Utilizzare gli altri campi forniti per impostare la conversione unità.</span><span class="sxs-lookup"><span data-stu-id="426fa-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="426fa-134">Seleziona **OK** per salvare la nuova conversione unità.</span><span class="sxs-lookup"><span data-stu-id="426fa-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="426fa-135">Puoi aprire la pagina **Conversioni unità** per un prodotto o una variante prodotto da una delle seguenti pagine:</span><span class="sxs-lookup"><span data-stu-id="426fa-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="426fa-136">Dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="426fa-136">Product details</span></span>
> - <span data-ttu-id="426fa-137">Dettagli prodotti rilasciato</span><span class="sxs-lookup"><span data-stu-id="426fa-137">Released products details</span></span>
> - <span data-ttu-id="426fa-138">Varianti prodotti rilasciati</span><span class="sxs-lookup"><span data-stu-id="426fa-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="426fa-139">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="426fa-139">Example scenario</span></span>

<span data-ttu-id="426fa-140">In questo scenario una società vende magliette di taglia S, M, L e XL.</span><span class="sxs-lookup"><span data-stu-id="426fa-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="426fa-141">La maglietta è definita come prodotto e le diverse taglie sono definite come varianti di tale prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="426fa-142">Le magliette sono confezionate in scatole.</span><span class="sxs-lookup"><span data-stu-id="426fa-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="426fa-143">Per la taglia S, M e L ogni scatola può contenere cinque magliette.</span><span class="sxs-lookup"><span data-stu-id="426fa-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="426fa-144">Tuttavia, per la taglia XL, c'è spazio per solo quattro magliette in ogni scatola.</span><span class="sxs-lookup"><span data-stu-id="426fa-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="426fa-145">La società desidera tenere traccia delle differenti varianti nell'unità *Pezzi* ma vende le magliette nell'unità *Scatole*.</span><span class="sxs-lookup"><span data-stu-id="426fa-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="426fa-146">Per la taglia S, M e L, la conversione tra unità di inventario e unità di vendita è 1 scatola = 5 pezzi.</span><span class="sxs-lookup"><span data-stu-id="426fa-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="426fa-147">Per la taglia XL, la conversione è 1 scatola = 4 pezzi.</span><span class="sxs-lookup"><span data-stu-id="426fa-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="426fa-148">Dalla pagina **Dettagli prodotto rilasciato** per il prodotto **Maglietta**, apri la pagina **Conversioni unità**.</span><span class="sxs-lookup"><span data-stu-id="426fa-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="426fa-149">Nella pagina **Conversioni unità**, configurare la seguente conversione unità per la variante prodotto rilasciata **XL**.</span><span class="sxs-lookup"><span data-stu-id="426fa-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="426fa-150">Campo</span><span class="sxs-lookup"><span data-stu-id="426fa-150">Field</span></span>                 | <span data-ttu-id="426fa-151">Impostazione</span><span class="sxs-lookup"><span data-stu-id="426fa-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="426fa-152">Crea conversione per</span><span class="sxs-lookup"><span data-stu-id="426fa-152">Create conversion for</span></span> | <span data-ttu-id="426fa-153">Variante prodotto</span><span class="sxs-lookup"><span data-stu-id="426fa-153">Product variant</span></span>         |
    | <span data-ttu-id="426fa-154">Variante prodotto</span><span class="sxs-lookup"><span data-stu-id="426fa-154">Product variant</span></span>       | <span data-ttu-id="426fa-155">Maglietta : : XL : :</span><span class="sxs-lookup"><span data-stu-id="426fa-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="426fa-156">Dall'unità</span><span class="sxs-lookup"><span data-stu-id="426fa-156">From unit</span></span>             | <span data-ttu-id="426fa-157">Scatole</span><span class="sxs-lookup"><span data-stu-id="426fa-157">Boxes</span></span>                   |
    | <span data-ttu-id="426fa-158">Fattore</span><span class="sxs-lookup"><span data-stu-id="426fa-158">Factor</span></span>                | <span data-ttu-id="426fa-159">4</span><span class="sxs-lookup"><span data-stu-id="426fa-159">4</span></span>                       |
    | <span data-ttu-id="426fa-160">All'unità</span><span class="sxs-lookup"><span data-stu-id="426fa-160">To Unit</span></span>               | <span data-ttu-id="426fa-161">Pezzi</span><span class="sxs-lookup"><span data-stu-id="426fa-161">Pieces</span></span>                  |

1. <span data-ttu-id="426fa-162">Tutte le varianti prodotto rilasciato **S**, **M** e **L** hanno la stessa conversione di unità tra l'unità *Scatola* e *Pezzi*, a significare che è possibile definire la conversione di unità seguente per queste varianti prodotto nella rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="426fa-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="426fa-163">Campo</span><span class="sxs-lookup"><span data-stu-id="426fa-163">Field</span></span>                 | <span data-ttu-id="426fa-164">Impostazione</span><span class="sxs-lookup"><span data-stu-id="426fa-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="426fa-165">Crea conversione per</span><span class="sxs-lookup"><span data-stu-id="426fa-165">Create conversion for</span></span> | <span data-ttu-id="426fa-166">Prodotto</span><span class="sxs-lookup"><span data-stu-id="426fa-166">Product</span></span> |
    | <span data-ttu-id="426fa-167">Prodotto</span><span class="sxs-lookup"><span data-stu-id="426fa-167">Product</span></span>               | <span data-ttu-id="426fa-168">Maglietta</span><span class="sxs-lookup"><span data-stu-id="426fa-168">T-Shirt</span></span> |
    | <span data-ttu-id="426fa-169">Dall'unità</span><span class="sxs-lookup"><span data-stu-id="426fa-169">From unit</span></span>             | <span data-ttu-id="426fa-170">Scatole</span><span class="sxs-lookup"><span data-stu-id="426fa-170">Boxes</span></span>   |
    | <span data-ttu-id="426fa-171">Fattore</span><span class="sxs-lookup"><span data-stu-id="426fa-171">Factor</span></span>                | <span data-ttu-id="426fa-172">5</span><span class="sxs-lookup"><span data-stu-id="426fa-172">5</span></span>       |
    | <span data-ttu-id="426fa-173">All'unità</span><span class="sxs-lookup"><span data-stu-id="426fa-173">To Unit</span></span>               | <span data-ttu-id="426fa-174">Pezzi</span><span class="sxs-lookup"><span data-stu-id="426fa-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="426fa-175">Utilizzo di Excel per aggiornare le conversioni di unità</span><span class="sxs-lookup"><span data-stu-id="426fa-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="426fa-176">Se un prodotto ha molte varianti di prodotto con conversioni di unità diverse, ti consigliamo di esportare le conversioni unità in una cartella di lavoro Microsoft Excel, aggiornarle e quindi pubblicarle nuovamente in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="426fa-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="426fa-177">Per esportare le conversioni unità in Excel, nella pagina **Conversioni unità**, nel riquadro azioni, seleziona **Apri in Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="426fa-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="426fa-178">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="426fa-178">Additional resources</span></span>

[<span data-ttu-id="426fa-179">Gestire unità di misura</span><span class="sxs-lookup"><span data-stu-id="426fa-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)
