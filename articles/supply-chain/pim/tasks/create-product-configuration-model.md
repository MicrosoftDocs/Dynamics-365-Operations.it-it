--- 
title: Crea un modello di configurazione prodotto
description: Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti.
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: d494a20ba6f1f9c33a3935779b4bd3a8eefce26a
ms.contentlocale: it-it
ms.lasthandoff: 11/14/2017

---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="f86fb-103">Crea un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="f86fb-103">Create a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f86fb-104">Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti.</span><span class="sxs-lookup"><span data-stu-id="f86fb-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="f86fb-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="f86fb-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="f86fb-106">Creare un modello prodotto</span><span class="sxs-lookup"><span data-stu-id="f86fb-106">Create a product model</span></span>
1. <span data-ttu-id="f86fb-107">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="f86fb-108">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="f86fb-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f86fb-109">Click New.</span></span>
4. <span data-ttu-id="f86fb-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f86fb-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f86fb-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="f86fb-112">Selezionare un'opzione nel campo Strategia risolutore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="f86fb-113">La strategia risolutore determina come vengono elaborati i vincoli di un modello di configurazione prodotto basata su vincoli.</span><span class="sxs-lookup"><span data-stu-id="f86fb-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="f86fb-114">Questa opzione può avere impatto sulle prestazioni del modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="f86fb-115">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f86fb-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="f86fb-116">Il componente radice rappresenta il modello di configurazione prodotto, ma può essere utilizzato in altri modelli prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="f86fb-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f86fb-117">Click OK.</span></span>
9. <span data-ttu-id="f86fb-118">Selezionare un'opzione nel campo Riutilizza configurazioni.</span><span class="sxs-lookup"><span data-stu-id="f86fb-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="f86fb-119">Se il parametro per riutilizzare le configurazioni è impostato su Sì, il sistema cercherà configurazioni identiche dopo ogni sessione di configurazione e riutilizzerà la corrispondenza esatta eventualmente rilevata.</span><span class="sxs-lookup"><span data-stu-id="f86fb-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="f86fb-120">Aggiungi attributi</span><span class="sxs-lookup"><span data-stu-id="f86fb-120">Add attributes</span></span>
1. <span data-ttu-id="f86fb-121">Espandere la sezione Attributi.</span><span class="sxs-lookup"><span data-stu-id="f86fb-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="f86fb-122">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f86fb-122">Click Add.</span></span>
3. <span data-ttu-id="f86fb-123">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f86fb-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="f86fb-124">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f86fb-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f86fb-125">Digitare un valore nel campo Nome risolutore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="f86fb-126">Il nome risolutore viene utilizzato dal risolutore vincolo della configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="f86fb-127">Non deve includere spazi o caratteri speciali, eccetto il carattere _ (sottolineatura).</span><span class="sxs-lookup"><span data-stu-id="f86fb-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="f86fb-128">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="f86fb-129">Il testo di descrizione viene visualizzato all'utente della configurazione e può pertanto essere utilizzato come guida nella selezione del valore di attributo corretto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="f86fb-130">Nel campo Tipo di attributo, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="f86fb-131">Il tipo di attributo determina i valori disponibili per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="f86fb-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="f86fb-132">Selezionare la casella di controllo Includi in riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="f86fb-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="f86fb-133">Questa opzione è disponibile solo se è selezionata l'opzione Riutilizza configurazioni.</span><span class="sxs-lookup"><span data-stu-id="f86fb-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="f86fb-134">Se si aggiunge l'attributo nella casella di controllo del riutilizzo, questo attributo verrà considerato quando il sistema effettua la ricerca della corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="f86fb-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="f86fb-135">Aggiungere sottocomponenti</span><span class="sxs-lookup"><span data-stu-id="f86fb-135">Add subcomponents</span></span>
1. <span data-ttu-id="f86fb-136">Espandere la sezione Sottocomponenti.</span><span class="sxs-lookup"><span data-stu-id="f86fb-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="f86fb-137">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f86fb-137">Click Add.</span></span>
3. <span data-ttu-id="f86fb-138">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f86fb-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="f86fb-139">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f86fb-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f86fb-140">Digitare un valore nel campo Nome risolutore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="f86fb-141">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="f86fb-142">Nel campo Componente immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="f86fb-143">Ogni sottocomponente deve fare riferimento a una definizione di componente.</span><span class="sxs-lookup"><span data-stu-id="f86fb-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="f86fb-144">La progettazione supporta i componenti riutilizzabili e garantisce che un componente definito possa essere utilizzato in più modelli prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="f86fb-145">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f86fb-145">Click Save.</span></span>
9. <span data-ttu-id="f86fb-146">Fare clic su Dettagli riga DBA.</span><span class="sxs-lookup"><span data-stu-id="f86fb-146">Click BOM line details.</span></span>
    * <span data-ttu-id="f86fb-147">Il modulo dei dettagli della riga DBA consente all'utente di selezionare le proprietà richieste per il sottocomponente.</span><span class="sxs-lookup"><span data-stu-id="f86fb-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="f86fb-148">Per ogni proprietà può essere specificato un valore fisso o sottoposto al mapping a un attributo.</span><span class="sxs-lookup"><span data-stu-id="f86fb-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="f86fb-149">Il mapping a un attributo determina che la proprietà riga DBA abbia valori diversi a seconda della selezione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="f86fb-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="f86fb-150">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f86fb-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="f86fb-151">Ogni sottocomponente rappresenta una rappresentazione generale prodotto configurabile con la tecnologia di configurazione basata su vincoli.</span><span class="sxs-lookup"><span data-stu-id="f86fb-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="f86fb-152">Il riferimento viene effettuato tramite il numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="f86fb-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="f86fb-153">Selezionare la casella di controllo Imposta.</span><span class="sxs-lookup"><span data-stu-id="f86fb-153">Select the Set check box.</span></span>
12. <span data-ttu-id="f86fb-154">Selezionare Sì nel campo Calcolo.</span><span class="sxs-lookup"><span data-stu-id="f86fb-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="f86fb-155">Impostando l'opzione di calcolo si garantisce che il prodotto venga incluso durante l'esecuzione di un calcolo dei costi per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="f86fb-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="f86fb-156">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f86fb-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="f86fb-157">Selezionare la casella di controllo Imposta.</span><span class="sxs-lookup"><span data-stu-id="f86fb-157">Select the Set check box.</span></span>
15. <span data-ttu-id="f86fb-158">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f86fb-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f86fb-159">Il campo della quantità determina la quantità del prodotto che verrà utilizzata nel prodotto configurato.</span><span class="sxs-lookup"><span data-stu-id="f86fb-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="f86fb-160">Selezionare la casella di controllo Imposta.</span><span class="sxs-lookup"><span data-stu-id="f86fb-160">Select the Set check box.</span></span>
17. <span data-ttu-id="f86fb-161">Nel campo Per serie, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f86fb-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="f86fb-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f86fb-162">Click OK.</span></span>


