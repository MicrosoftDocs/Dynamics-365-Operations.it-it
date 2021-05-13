---
title: Creare una gerarchia di navigazione nei canali
description: In questo argomento viene descritto come creare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5df46de9dadfa0b7160a9b340ef36fdf963a0ad3
ms.sourcegitcommit: 6c2f5c3b038f696532c335e20b0fbafa155d6858
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "5951910"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="b69da-103">Creare una gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="b69da-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b69da-104">In questo argomento viene descritto come creare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b69da-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b69da-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b69da-105">Overview</span></span>

<span data-ttu-id="b69da-106">Una gerarchia di navigazione nei canali è utilizzata per raggruppare e organizzare prodotti in categorie di modo che i prodotti possano essere esaminati online o nel POS.</span><span class="sxs-lookup"><span data-stu-id="b69da-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="b69da-107">Creare una gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="b69da-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="b69da-108">Per creare una gerarchia di navigazione nei canali, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="b69da-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="b69da-109">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Categorie di navigazione nei canali**.</span><span class="sxs-lookup"><span data-stu-id="b69da-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="b69da-110">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b69da-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b69da-111">Nella casella **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="b69da-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="b69da-112">Nella casella **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b69da-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="b69da-113">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b69da-113">Select **Create**.</span></span>
1. <span data-ttu-id="b69da-114">Nel riquadro azioni selezionare **Nuovo nodo di categoria** per creare un nodo principale.</span><span class="sxs-lookup"><span data-stu-id="b69da-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="b69da-115">Nella casella **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="b69da-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="b69da-116">Nella casella **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b69da-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="b69da-117">Nella casella **Nome descrittivo** immettere un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="b69da-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="b69da-118">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b69da-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b69da-119">L'immagine seguente mostra un esempio di nodo principale.</span><span class="sxs-lookup"><span data-stu-id="b69da-119">The following image shows a example root node.</span></span>

![Esempio di nodo principale](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="b69da-121">Creare nodi di categoria di navigazione</span><span class="sxs-lookup"><span data-stu-id="b69da-121">Create navigation category nodes</span></span>

<span data-ttu-id="b69da-122">Per creare eventuali nodi di categoria di navigazione aggiuntivi per rappresentare le categorie di prodotti nel canale, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b69da-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="b69da-123">Nel pannello di navigazione, selezionare il nodo padre a cui aggiungere una categoria.</span><span class="sxs-lookup"><span data-stu-id="b69da-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="b69da-124">Nel riquadro Azioni selezionare **Nuovo nodo di categoria**.</span><span class="sxs-lookup"><span data-stu-id="b69da-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="b69da-125">Nella casella **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="b69da-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="b69da-126">Nella casella **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b69da-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="b69da-127">Nella casella **Nome descrittivo** immettere un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="b69da-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="b69da-128">Nella casella **Ordine di visualizzazione**, inserire un ordine di visualizzazione (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="b69da-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="b69da-129">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b69da-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b69da-130">L'immagine seguente mostra un esempio di gerarchia di navigazione nei canali completata.</span><span class="sxs-lookup"><span data-stu-id="b69da-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Esempio di gerarchia dei canali](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="b69da-132">Aggiungere prodotti a nodi di categorie</span><span class="sxs-lookup"><span data-stu-id="b69da-132">Add products to category nodes</span></span>

<span data-ttu-id="b69da-133">Per aggiungere prodotti a nodi di categoria, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b69da-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="b69da-134">Selezionare un nodo di categoria.</span><span class="sxs-lookup"><span data-stu-id="b69da-134">Select a category node.</span></span>
1. <span data-ttu-id="b69da-135">Sotto **Prodotti**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b69da-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="b69da-136">Trovare i nuovi prodotti che si desidera aggiungere utilizzando il numero o il nome di prodotto, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b69da-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="b69da-137">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b69da-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b69da-138">L'aggiunta di prodotti a un nodo all'interno della gerarchia di navigazione nei canali non è sufficiente per visualizzare i prodotti in un canale selezionato in quanto i prodotti devono anche essere assortiti in un canale.</span><span class="sxs-lookup"><span data-stu-id="b69da-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a channel.</span></span> <span data-ttu-id="b69da-139">Per ulteriori informazioni sugli assortimenti, vedere [Gestione dell'assortimento](assortments.md).</span><span class="sxs-lookup"><span data-stu-id="b69da-139">For more information on assortments, see [Assortment management](assortments.md).</span></span>

<span data-ttu-id="b69da-140">L'immagine seguente mostra un esempio di nodo con prodotti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="b69da-140">The following image shows an example node with products added.</span></span>

![Prodotti aggiunti a un nodo di categoria](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="b69da-142">Aggiungere gruppi di attributi di prodotto a nodi di categoria</span><span class="sxs-lookup"><span data-stu-id="b69da-142">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="b69da-143">I gruppi di attributi devono essere creati prima di poterli aggiungere a un nodo in una gerarchia di navigazione nei canali.</span><span class="sxs-lookup"><span data-stu-id="b69da-143">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="b69da-144">Per aggiungere un gruppo di attributi di prodotto a un nodo di categoria, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="b69da-144">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="b69da-145">Selezionare un nodo di categoria.</span><span class="sxs-lookup"><span data-stu-id="b69da-145">Select a category node.</span></span>
1. <span data-ttu-id="b69da-146">Sotto **Gruppi di attributi del prodotto**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b69da-146">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="b69da-147">Trovare i gruppi di attributi che si desidera aggiungere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b69da-147">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="b69da-148">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b69da-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b69da-149">L'immagine seguente mostra un esempio di nodo con gruppi di attributi di prodotto aggiunti.</span><span class="sxs-lookup"><span data-stu-id="b69da-149">The following image shows a sample node with product attribute groups added.</span></span>

![Gruppi di attributi di prodotto in un nodo](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="b69da-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b69da-151">Additional resources</span></span>

[<span data-ttu-id="b69da-152">Impostare assortimenti</span><span class="sxs-lookup"><span data-stu-id="b69da-152">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="b69da-153">Gestire attributi e gruppi di attributi</span><span class="sxs-lookup"><span data-stu-id="b69da-153">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
