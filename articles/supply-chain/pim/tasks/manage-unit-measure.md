---
title: Gestire unità di misura
description: Questo argomento descrive come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921343"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="dcba7-103">Gestire unità di misura</span><span class="sxs-lookup"><span data-stu-id="dcba7-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dcba7-104">Questo argomento descrive come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate.</span><span class="sxs-lookup"><span data-stu-id="dcba7-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="dcba7-105">Aprire la pagina Unità</span><span class="sxs-lookup"><span data-stu-id="dcba7-105">Open the Units page</span></span>

<span data-ttu-id="dcba7-106">Per creare e lavorare con le unità di misura disponibili nel tuo sistema, vai a **Amministrazione organizzazione \> Impostazioni \> Unità \> Unità**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="dcba7-107">Le sezioni rimanenti di questo argomento descrivono cosa è possibile fare nella pagina **Unità**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="dcba7-108">Creare unità e conversioni standard</span><span class="sxs-lookup"><span data-stu-id="dcba7-108">Create standard units and conversions</span></span>

<span data-ttu-id="dcba7-109">Se il tuo sistema non include già le unità di misura più comunemente utilizzate per il sistema metrico e / o US Customary System (USCS), la procedura guidata di configurazione delle unità può aiutarti a iniziare rapidamente con le definizioni e le conversioni di unità di base.</span><span class="sxs-lookup"><span data-stu-id="dcba7-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="dcba7-110">Per completare la procedura guidata, seleziona **Creazione guidata unità** nel riquadro azioni, quindi seguire le istruzioni sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="dcba7-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="dcba7-111">Creare o modificare un'unità di misura</span><span class="sxs-lookup"><span data-stu-id="dcba7-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="dcba7-112">Per creare o modificare un'unità di misura, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="dcba7-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="dcba7-113">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="dcba7-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="dcba7-114">Per modificare un'unità esistente, selezionala nel riquadro elenco.</span><span class="sxs-lookup"><span data-stu-id="dcba7-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="dcba7-115">Nel riquadro azioni seleziona **Nuovo** per creare una nuova unità.</span><span class="sxs-lookup"><span data-stu-id="dcba7-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="dcba7-116">Nell'intestazione del record, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="dcba7-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="dcba7-117">**Unità** - Immettere l'ID o il simbolo da utilizzare per fare riferimento all'unità nella lingua del sistema.</span><span class="sxs-lookup"><span data-stu-id="dcba7-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="dcba7-118">Questo ID o simbolo è solitamente un'abbreviazione comune per l'unità, ad esempio *pz* per pezzo o *cm* per centimetro.</span><span class="sxs-lookup"><span data-stu-id="dcba7-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="dcba7-119">**Descrizione** – Immettere un nome descrittivo dell'unità nella lingua del sistema.</span><span class="sxs-lookup"><span data-stu-id="dcba7-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="dcba7-120">Questo nome è solitamente il nome completo dell'unità, ad esempio *Pezzo* o *Centimetro*.</span><span class="sxs-lookup"><span data-stu-id="dcba7-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="dcba7-121">Nella scheda dettaglio **Generale**, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="dcba7-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="dcba7-122">**Classe di unità di misura** - Selezionare la proprietà misurata dall'unità (come lunghezza, area, massa o quantità).</span><span class="sxs-lookup"><span data-stu-id="dcba7-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="dcba7-123">**Sistema di misurazione** - Selezionare il sistema di misurazione a cui appartiene l'unità (*Unità sistema metrico decimale* o *Unità sistema di misura USA*).</span><span class="sxs-lookup"><span data-stu-id="dcba7-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="dcba7-124">**Unità di base** - Imposta questa opzione su *Sì* per utilizzare l'unità corrente come unità di base per la sua classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="dcba7-125">In questo caso, devi solo specificare il fattore di conversione tra l'unità di base e ogni unità aggiuntiva nella classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="dcba7-126">Il sistema può quindi convertire tra tutte le unità in quella classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="dcba7-127">Pertanto, è più facile impostare le conversioni.</span><span class="sxs-lookup"><span data-stu-id="dcba7-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="dcba7-128">Ad esempio, se gallone è l'unità di base per la classe di unità di misura *Volume*, devi solo impostare i fattori di conversione da quarto a gallone e da pinta a gallone.</span><span class="sxs-lookup"><span data-stu-id="dcba7-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="dcba7-129">Il sistema può quindi anche convertire da un quarto a una pinta.</span><span class="sxs-lookup"><span data-stu-id="dcba7-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="dcba7-130">Puoi avere una sola unità di base per classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="dcba7-131">**Unità di sistema** - Imposta questa opzione su *Sì* per utilizzare l'unità corrente come unità presunta per tutte le misurazioni non specificate nella sua classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="dcba7-132">Ad esempio, se un campo utilizzato per immettere una quantità non consente di specificare un'unità (o se l'utente non seleziona un'unità), il sistema utilizza l'unità impostata come unità di sistema per la classe di unità di misura *Quantità*.</span><span class="sxs-lookup"><span data-stu-id="dcba7-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="dcba7-133">Puoi avere una sola unità di sistema per classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="dcba7-134">**Precisione decimale** - Specificare il numero di cifre decimali a cui arrotondare i valori specificati per l'unità corrente o convertiti in essa.</span><span class="sxs-lookup"><span data-stu-id="dcba7-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="dcba7-135">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="dcba7-136">Definire conversioni unità</span><span class="sxs-lookup"><span data-stu-id="dcba7-136">Define unit translations</span></span>

<span data-ttu-id="dcba7-137">Per definire le traduzioni per l'ID o il simbolo e la descrizione per un'unità di misura, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="dcba7-138">Crea o seleziona l'unità per cui creare le traduzioni.</span><span class="sxs-lookup"><span data-stu-id="dcba7-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="dcba7-139">Nel riquadro azioni, seleziona **Testi unità**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="dcba7-140">Viene visualizzata la pagina **Testi unità**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="dcba7-141">Utilizzare questa pagina per definire le traduzioni per l'ID o il simbolo per l'unità selezionata.</span><span class="sxs-lookup"><span data-stu-id="dcba7-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="dcba7-142">Tali traduzioni possono quindi essere utilizzate su documenti esterni in lingue specifiche del cliente o del fornitore.</span><span class="sxs-lookup"><span data-stu-id="dcba7-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="dcba7-143">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="dcba7-144">Nel campo **Lingua** selezionare la lingua in cui tradurre l'ID o il simbolo dell'unità.</span><span class="sxs-lookup"><span data-stu-id="dcba7-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="dcba7-145">Nel campo **Testo** campo, inserire la traduzione dell'ID unità o del simbolo nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="dcba7-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="dcba7-146">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="dcba7-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dcba7-147">Close the page.</span></span>
1. <span data-ttu-id="dcba7-148">Nel **riquadro azioni** fai clic su **Descrizioni unità convertite**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="dcba7-149">La pagina **Descrizioni unità convertite** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="dcba7-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="dcba7-150">Utilizzare questa pagina per definire le descrizioni specifiche della lingua per l'unità selezionata.</span><span class="sxs-lookup"><span data-stu-id="dcba7-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="dcba7-151">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="dcba7-152">Nel campo **Lingua** selezionare la lingua in cui tradurre la descrizione dell'unità.</span><span class="sxs-lookup"><span data-stu-id="dcba7-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="dcba7-153">Nel campo **Descrizione** campo, inserire la traduzione della descrizione unità nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="dcba7-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="dcba7-154">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="dcba7-155">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dcba7-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="dcba7-156">Definire regole di conversione unità</span><span class="sxs-lookup"><span data-stu-id="dcba7-156">Define unit conversion rules</span></span>

<span data-ttu-id="dcba7-157">Per definire le regole per le conversioni tra unità di misura, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="dcba7-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="dcba7-158">Crea o seleziona l'unità per cui definire le regole di conversione.</span><span class="sxs-lookup"><span data-stu-id="dcba7-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="dcba7-159">Nel riquadro azioni, seleziona **Conversioni unità**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="dcba7-160">Viene aperta la pagina **Conversioni unità**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="dcba7-161">Usa questa pagina per fefinire le regole per la conversione dell'unità selezionata verso e da altre unità di misura incluse nella classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="dcba7-162">Selezionare una delle schede seguenti a seconda del tipo di conversione da impostare:</span><span class="sxs-lookup"><span data-stu-id="dcba7-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="dcba7-163">**Conversioni standard** – Consente di impostare le regole di conversione standard per tutti i prodotti.</span><span class="sxs-lookup"><span data-stu-id="dcba7-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="dcba7-164">**Conversioni in classi** - Consente di impostare le regole di conversione specifiche di un prodotto per le unità appartenenti alla stessa classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="dcba7-165">**Conversioni tra classi** - Consente di impostare le regole di conversione specifiche di un prodotto per le unità di diverse classi di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="dcba7-166">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="dcba7-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="dcba7-167">Nella barra degli strumenti seleziona **Nuovo** per creare una nuova conversione.</span><span class="sxs-lookup"><span data-stu-id="dcba7-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="dcba7-168">Per modificare una conversione esistente, seleziona la conversione nella griglia, quindi seleziona **Modifica** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="dcba7-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="dcba7-169">Nella finestra di dialogo a discesa visualizzata, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="dcba7-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="dcba7-170">**Prodotto** - Seleziona il prodotto specifico a cui si applica la conversione.</span><span class="sxs-lookup"><span data-stu-id="dcba7-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="dcba7-171">Questo campo è disponibile solo per conversioni in classi e tra classi.</span><span class="sxs-lookup"><span data-stu-id="dcba7-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="dcba7-172">**Layout formula** - Lascia questo campo impostato su *Semplice* per specificare una semplice conversione che ha un singolo fattore.</span><span class="sxs-lookup"><span data-stu-id="dcba7-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="dcba7-173">Impostalo su *Avanzato* per impostare un'equazione più complessa.</span><span class="sxs-lookup"><span data-stu-id="dcba7-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="dcba7-174">Il formato per le equazioni avanzate varia a seconda della classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="dcba7-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="dcba7-175">**Dall'unità** - Questo campo mostra l'unità selezionata.</span><span class="sxs-lookup"><span data-stu-id="dcba7-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="dcba7-176">Di solito, non dovresti modificare il valore.</span><span class="sxs-lookup"><span data-stu-id="dcba7-176">Usually, you should not change the value.</span></span> <span data-ttu-id="dcba7-177">(Se modifichi il valore, devi aprire la pagina **Conversioni unità** per l'unità selezionata per visualizzare la nuova conversione dopo averla salvata.)</span><span class="sxs-lookup"><span data-stu-id="dcba7-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="dcba7-178">**All'unità** - Seleziona l'unità in cui convertire.</span><span class="sxs-lookup"><span data-stu-id="dcba7-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="dcba7-179">**Arrotondamento** - Seleziona come arrotondare le frazioni, in base al valore **Precisione decimale** dell'unità selezionata (*All'unità più vicina*, *Per eccesso*, o *Per difetto*).</span><span class="sxs-lookup"><span data-stu-id="dcba7-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="dcba7-180">**Formula di conversione** - Utilizzare i campi rimanenti nella parte superiore della finestra di dialogo a discesa per specificare la formula per la conversione tra le due unità.</span><span class="sxs-lookup"><span data-stu-id="dcba7-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="dcba7-181">I campi disponibili variano a seconda della classe di unità di misura e del layout della formula selezionati.</span><span class="sxs-lookup"><span data-stu-id="dcba7-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="dcba7-182">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcba7-182">Select **OK**.</span></span>
1. <span data-ttu-id="dcba7-183">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dcba7-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="dcba7-184">Puoi anche impostare conversioni di unità per variante di prodotto.</span><span class="sxs-lookup"><span data-stu-id="dcba7-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="dcba7-185">Per ulteriori informazioni, vedere [Conversione di unità di misura per varianti prodotto](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="dcba7-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
