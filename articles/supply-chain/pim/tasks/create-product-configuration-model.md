---
title: Crea un modello di configurazione prodotto
description: Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921367"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="1a077-103">Crea un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="1a077-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1a077-104">Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti.</span><span class="sxs-lookup"><span data-stu-id="1a077-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="1a077-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="1a077-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="1a077-106">Creare un modello prodotto</span><span class="sxs-lookup"><span data-stu-id="1a077-106">Create a product model</span></span>

1. <span data-ttu-id="1a077-107">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="1a077-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="1a077-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1a077-108">Select **New**.</span></span>
1. <span data-ttu-id="1a077-109">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1a077-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="1a077-110">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1a077-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="1a077-111">Selezionare un'opzione nel campo **Strategia risolutore**.</span><span class="sxs-lookup"><span data-stu-id="1a077-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="1a077-112">La strategia risolutore determina come vengono elaborati i vincoli di un modello di configurazione prodotto basata su vincoli.</span><span class="sxs-lookup"><span data-stu-id="1a077-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="1a077-113">Questa opzione può avere impatto sulle prestazioni del modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="1a077-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="1a077-114">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1a077-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="1a077-115">Il componente radice rappresenta il modello di configurazione prodotto, ma può essere utilizzato in altri modelli prodotto.</span><span class="sxs-lookup"><span data-stu-id="1a077-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="1a077-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a077-116">Select **OK**.</span></span>
1. <span data-ttu-id="1a077-117">Selezionare un'opzione nel campo **Riutilizza configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="1a077-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="1a077-118">Se il parametro per riutilizzare le configurazioni è impostato su Sì, il sistema cercherà configurazioni identiche dopo ogni sessione di configurazione e riutilizzerà la corrispondenza esatta eventualmente rilevata.</span><span class="sxs-lookup"><span data-stu-id="1a077-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="1a077-119">Aggiungi attributi</span><span class="sxs-lookup"><span data-stu-id="1a077-119">Add attributes</span></span>

1. <span data-ttu-id="1a077-120">Espandere la sezione **Attributi**.</span><span class="sxs-lookup"><span data-stu-id="1a077-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="1a077-121">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1a077-121">Select **Add**.</span></span>
3. <span data-ttu-id="1a077-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a077-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="1a077-123">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1a077-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="1a077-124">Digitare un valore nel campo **Nome risolutore**.</span><span class="sxs-lookup"><span data-stu-id="1a077-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="1a077-125">Il nome risolutore viene utilizzato dal risolutore vincolo della configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="1a077-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="1a077-126">Non deve includere spazi o caratteri speciali, eccetto il carattere _ (sottolineatura).</span><span class="sxs-lookup"><span data-stu-id="1a077-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="1a077-127">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1a077-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="1a077-128">Il testo di descrizione viene visualizzato all'utente della configurazione e può pertanto essere utilizzato come guida nella selezione del valore di attributo corretto.</span><span class="sxs-lookup"><span data-stu-id="1a077-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="1a077-129">Nel campo **Tipo di attributo**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a077-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="1a077-130">Il tipo di attributo determina i valori disponibili per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="1a077-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="1a077-131">Selezionare la casella di controllo **Includi in riutilizzo**.</span><span class="sxs-lookup"><span data-stu-id="1a077-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="1a077-132">Questa opzione è disponibile solo se è selezionata l'opzione Riutilizza configurazioni.</span><span class="sxs-lookup"><span data-stu-id="1a077-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="1a077-133">Se si aggiunge l'attributo nella casella di controllo del riutilizzo, questo attributo verrà considerato quando il sistema effettua la ricerca della corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="1a077-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="1a077-134">Aggiungere sottocomponenti</span><span class="sxs-lookup"><span data-stu-id="1a077-134">Add subcomponents</span></span>

1. <span data-ttu-id="1a077-135">Espandere la sezione **Sottocomponenti**.</span><span class="sxs-lookup"><span data-stu-id="1a077-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="1a077-136">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1a077-136">Select **Add**.</span></span>
3. <span data-ttu-id="1a077-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a077-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="1a077-138">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1a077-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="1a077-139">Digitare un valore nel campo **Nome risolutore**.</span><span class="sxs-lookup"><span data-stu-id="1a077-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="1a077-140">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1a077-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="1a077-141">Nel campo **Componente** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a077-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="1a077-142">Ogni sottocomponente deve fare riferimento a una definizione di componente.</span><span class="sxs-lookup"><span data-stu-id="1a077-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="1a077-143">La progettazione supporta i componenti riutilizzabili e garantisce che un componente definito possa essere utilizzato in più modelli prodotto.</span><span class="sxs-lookup"><span data-stu-id="1a077-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="1a077-144">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1a077-144">Select **Save**.</span></span>
9. <span data-ttu-id="1a077-145">Selezionare **Dettagli riga DBA**.</span><span class="sxs-lookup"><span data-stu-id="1a077-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="1a077-146">Il modulo dei dettagli della riga DBA consente all'utente di selezionare le proprietà richieste per il sottocomponente.</span><span class="sxs-lookup"><span data-stu-id="1a077-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="1a077-147">Per ogni proprietà può essere specificato un valore fisso o sottoposto al mapping a un attributo.</span><span class="sxs-lookup"><span data-stu-id="1a077-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="1a077-148">Il mapping a un attributo determina che la proprietà riga DBA abbia valori diversi a seconda della selezione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="1a077-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="1a077-149">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a077-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="1a077-150">Ogni sottocomponente rappresenta una rappresentazione generale prodotto configurabile con la tecnologia di configurazione basata su vincoli.</span><span class="sxs-lookup"><span data-stu-id="1a077-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="1a077-151">Il riferimento viene effettuato tramite il numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="1a077-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="1a077-152">Selezionare la casella di controllo **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="1a077-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="1a077-153">Selezionare **Sì** nel campo **Calcolo**.</span><span class="sxs-lookup"><span data-stu-id="1a077-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="1a077-154">Impostando l'opzione di calcolo si garantisce che il prodotto venga incluso durante l'esecuzione di un calcolo dei costi per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1a077-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="1a077-155">Seleziona la scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="1a077-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="1a077-156">Selezionare la casella di controllo **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="1a077-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="1a077-157">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a077-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="1a077-158">Il campo della quantità determina la quantità del prodotto che verrà utilizzata nel prodotto configurato.</span><span class="sxs-lookup"><span data-stu-id="1a077-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="1a077-159">Selezionare la casella di controllo **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="1a077-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="1a077-160">Nel campo **Per serie**, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a077-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="1a077-161">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a077-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]