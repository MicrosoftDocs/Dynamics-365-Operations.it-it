---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate
description: In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921013"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="bac4e-103">Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate</span><span class="sxs-lookup"><span data-stu-id="bac4e-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bac4e-104">In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile.</span><span class="sxs-lookup"><span data-stu-id="bac4e-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="bac4e-105">Questa procedura dimostra anche come è possibile creare una nomenclatura di configurazione per un componente del modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="bac4e-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="bac4e-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="bac4e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bac4e-107">La nuova nomenclatura di numero prodotto è assegnata alla rappresentazione generale prodotto D0004.</span><span class="sxs-lookup"><span data-stu-id="bac4e-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="bac4e-108">Questa attività viene in genere effettuata da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="bac4e-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="bac4e-109">Creare una nomenclatura di numero prodotto</span><span class="sxs-lookup"><span data-stu-id="bac4e-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="bac4e-110">Vai a **Gestione informazioni sul prodotto \> Imposta \> Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="bac4e-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-111">Select **New**.</span></span>
1. <span data-ttu-id="bac4e-112">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-113">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bac4e-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-114">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-114">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-115">Selezionare **Numero rappresentazione generale prodotto**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="bac4e-116">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-116">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-117">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="bac4e-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-119">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-120">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-120">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-121">Seleziona **Configurazione**</span><span class="sxs-lookup"><span data-stu-id="bac4e-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="bac4e-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac4e-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="bac4e-123">Assegnare la nomenclatura di un numero prodotto a una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="bac4e-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="bac4e-124">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="bac4e-125">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="bac4e-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="bac4e-126">Ad esempio, filtrare in base al campo **Numero prodotto** con un valore di 'D'.</span><span class="sxs-lookup"><span data-stu-id="bac4e-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="bac4e-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="bac4e-128">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-128">Select **Edit**.</span></span>
1. <span data-ttu-id="bac4e-129">Selezionare *Sì* nel campo **Utilizza nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="bac4e-130">Nel campo **Nomenclatura di numero di variante prodotto** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bac4e-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="bac4e-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac4e-131">Close the page.</span></span>
1. <span data-ttu-id="bac4e-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac4e-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="bac4e-133">Creare una nomenclatura per un componente di modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="bac4e-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="bac4e-134">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="bac4e-135">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="bac4e-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="bac4e-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="bac4e-137">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-137">Select **Edit**.</span></span>
1. <span data-ttu-id="bac4e-138">Selezionare *Sì* nel campo **Utilizza nomenclatura di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="bac4e-139">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-139">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-140">Selezionare **Valore attributo**</span><span class="sxs-lookup"><span data-stu-id="bac4e-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="bac4e-141">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-142">Nel campo **Attributo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bac4e-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="bac4e-143">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-143">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-144">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="bac4e-145">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-146">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-147">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-147">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-148">Selezionare **Valore attributo**</span><span class="sxs-lookup"><span data-stu-id="bac4e-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="bac4e-149">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-150">Nel campo **Attributo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bac4e-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="bac4e-151">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-151">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-152">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="bac4e-153">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-154">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-155">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-155">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-156">Selezionare **Valore attributo**</span><span class="sxs-lookup"><span data-stu-id="bac4e-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="bac4e-157">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-158">Nel campo **Attributo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bac4e-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="bac4e-159">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-159">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-160">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="bac4e-161">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-162">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-163">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-163">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-164">Selezionare **Valore attributo**</span><span class="sxs-lookup"><span data-stu-id="bac4e-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="bac4e-165">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-166">Nel campo **Attributo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bac4e-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="bac4e-167">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-167">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-168">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="bac4e-169">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-170">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="bac4e-171">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-171">Select **Add**.</span></span>
1. <span data-ttu-id="bac4e-172">Selezionare **Valore sequenza numerica**.</span><span class="sxs-lookup"><span data-stu-id="bac4e-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="bac4e-173">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bac4e-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bac4e-174">Nel campo **Sequenza numerica** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bac4e-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="bac4e-175">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac4e-175">Close the page.</span></span>
1. <span data-ttu-id="bac4e-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac4e-176">Close the page.</span></span>
1. <span data-ttu-id="bac4e-177">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac4e-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]