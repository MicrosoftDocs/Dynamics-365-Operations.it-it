---
title: Creare un nuova gerarchia di prodotti
description: In questo argomento viene descritto come creare un nuova gerarchia di prodotti in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 540a4a9c48ed958abb56a393e99b8060e1b7aa8e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207873"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="b2cad-103">Creare una nuova gerarchia prodotti</span><span class="sxs-lookup"><span data-stu-id="b2cad-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b2cad-104">In questo argomento viene descritto come creare un nuova gerarchia di prodotti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b2cad-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b2cad-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b2cad-105">Overview</span></span>

<span data-ttu-id="b2cad-106">In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b2cad-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="b2cad-107">Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="b2cad-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="b2cad-108">Ogni canale di vendita al dettaglio può disporre di propri metodi di pagamento, gruppi di prezzi, POS, conti ricavi/spese e personale.</span><span class="sxs-lookup"><span data-stu-id="b2cad-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="b2cad-109">È necessario impostare tutti questi elementi prima di creare un canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b2cad-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="b2cad-110">Una gerarchia di prodotti di Commerce è utilizzata per definire la gerarchia di prodotti generale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2cad-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="b2cad-111">È possibile utilizzare una gerarchia di prodotti di Commerce per il merchandising, la determinazione dei prezzi, le promozioni, il reporting e la pianificazione degli assortimenti.</span><span class="sxs-lookup"><span data-stu-id="b2cad-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="b2cad-112">A un'organizzazione può essere assegnata una sola gerarchia di prodotti di Commerce.</span><span class="sxs-lookup"><span data-stu-id="b2cad-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="b2cad-113">Creare e configurare una nuova gerarchia di prodotti</span><span class="sxs-lookup"><span data-stu-id="b2cad-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="b2cad-114">Per creare e configurare una gerarchia di prodotti Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="b2cad-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="b2cad-115">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Gerarchia di prodotti Commerce**.</span><span class="sxs-lookup"><span data-stu-id="b2cad-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="b2cad-116">Se non esiste ancora alcuna gerarchia, nel **riquadro azioni**, selezionare **Nuovo** per creare la radice della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b2cad-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="b2cad-117">Sotto **Generale**:</span><span class="sxs-lookup"><span data-stu-id="b2cad-117">Under **General**:</span></span>
    1. <span data-ttu-id="b2cad-118">Nella casella **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="b2cad-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="b2cad-119">Nella casella **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b2cad-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="b2cad-120">Nella casella **Nome descrittivo** immettere un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="b2cad-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="b2cad-121">Impostare **Attivo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b2cad-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="b2cad-122">Aggiungere nodi di gerarchia</span><span class="sxs-lookup"><span data-stu-id="b2cad-122">Add hierarchy nodes</span></span>

<span data-ttu-id="b2cad-123">Per aggiungere nodi di gerarchia, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b2cad-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="b2cad-124">Nel riquadro Azioni selezionare **Modifica gerarchia di categorie**.</span><span class="sxs-lookup"><span data-stu-id="b2cad-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="b2cad-125">Selezionare il nodo principale a cui si desidera aggiungere un nuovo nodo, quindi selezionare **Nuovo nodo di categoria**.</span><span class="sxs-lookup"><span data-stu-id="b2cad-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="b2cad-126">Nella sezione **Generale** la sezione fornisce **Nome**, **Descrizione**, **Nome descrittivo** e **Parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="b2cad-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="b2cad-127">Sotto **Generale**:</span><span class="sxs-lookup"><span data-stu-id="b2cad-127">Under **General**:</span></span>
    1. <span data-ttu-id="b2cad-128">Nella casella **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="b2cad-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="b2cad-129">Nella casella **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b2cad-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="b2cad-130">Nella casella **Nome descrittivo** immettere un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="b2cad-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="b2cad-131">Nella casella **Parole chiave**, inserire le parole chiave pertinenti.</span><span class="sxs-lookup"><span data-stu-id="b2cad-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="b2cad-132">Nella casella **Ordine di visualizzazione**, inserire un numero per l'ordine di visualizzazione (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="b2cad-132">In the **Display order** box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="b2cad-133">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b2cad-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="b2cad-134">Ripetere i passaggi precedenti per aggiungere altri nodi.</span><span class="sxs-lookup"><span data-stu-id="b2cad-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="b2cad-135">L'immagine seguente mostra la creazione di un nuovo nodo di gerarchia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="b2cad-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Creare un gerarchia di prodotti](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="b2cad-137">Altre impostazioni</span><span class="sxs-lookup"><span data-stu-id="b2cad-137">Other settings</span></span>

<span data-ttu-id="b2cad-138">I gruppi di attributi di categoria possono anche essere assegnati a ogni gruppo come richiesto.</span><span class="sxs-lookup"><span data-stu-id="b2cad-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="b2cad-139">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b2cad-139">Additional resources</span></span>

[<span data-ttu-id="b2cad-140">gerarchie commerce</span><span class="sxs-lookup"><span data-stu-id="b2cad-140">commerce hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="b2cad-141">Gestire le categorie di prodotti e i prodotti</span><span class="sxs-lookup"><span data-stu-id="b2cad-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="b2cad-142">Modificare l'ordinamento di visualizzazione per entità di merchandising</span><span class="sxs-lookup"><span data-stu-id="b2cad-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]