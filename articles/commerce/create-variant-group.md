---
title: Creare un gruppo di varianti
description: In questo argomento viene descritto come creare un gruppo di varianti di dimensioni, stile o colore per un prodotto in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d9279e1076796bb455429e5ff004c89ec5829e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413454"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="d9936-103">Creare un gruppo di varianti</span><span class="sxs-lookup"><span data-stu-id="d9936-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d9936-104">In questo argomento viene descritto come creare un gruppo di varianti di dimensioni, stile o colore per un prodotto in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d9936-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d9936-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d9936-105">Overview</span></span>

<span data-ttu-id="d9936-106">Dynamics 365 Commerce supporta molteplici varianti per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="d9936-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="d9936-107">È ideale per impostare gruppi di varianti per diverse categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="d9936-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="d9936-108">Ad esempio, è possibile creare un gruppo di dimensioni per magliette con taglie XS, S, M, L e XL, oppure un gruppo di colori per includere tutti i colori disponibili di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="d9936-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="d9936-109">I gruppi di varianti devono essere aggiunti prima dell'aggiunta dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="d9936-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="d9936-110">In questo argomento, verrà creato e configurato un gruppo di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d9936-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="d9936-111">Procedure simili possono essere utilizzate per aggiungere e configurare gruppi di stili e gruppi di colori.</span><span class="sxs-lookup"><span data-stu-id="d9936-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="d9936-112">Creare un gruppo di dimensioni</span><span class="sxs-lookup"><span data-stu-id="d9936-112">Create a size group</span></span>

<span data-ttu-id="d9936-113">Per creare un gruppo di dimensioni, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d9936-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="d9936-114">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Gruppi di varianti \> Gruppi di dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="d9936-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="d9936-115">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d9936-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d9936-116">Nella casella **Gruppo di dimensioni**, immettere un nome per il gruppo di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d9936-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="d9936-117">Immettere una descrizione appropriata nella casella **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="d9936-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="d9936-118">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d9936-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="d9936-119">Aggiungere attributi al gruppo di dimensioni</span><span class="sxs-lookup"><span data-stu-id="d9936-119">Add attributes to the size group</span></span>

<span data-ttu-id="d9936-120">Per aggiungere attributi a un gruppo di dimensioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="d9936-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="d9936-121">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Gruppi di varianti \> Gruppi di dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="d9936-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="d9936-122">Nel pannello di navigazione, selezionare un gruppo di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d9936-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="d9936-123">Sotto **Righe gruppo di dimensioni**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d9936-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="d9936-124">Nella casella **Dimensioni**, immettere una stringa che rappresenta la dimensione (ad esempio, "XL").</span><span class="sxs-lookup"><span data-stu-id="d9936-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="d9936-125">Nella casella **Nome dimensione**, inserire un nome per la dimensione (ad esempio, "Extra Large").</span><span class="sxs-lookup"><span data-stu-id="d9936-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="d9936-126">Nella casella **Peso rifornimento**, inserire un numero che rappresenta il peso di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="d9936-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="d9936-127">Nella casella **Numero nel codice a barre**, inserire un numero che rappresenta il codice a barre.</span><span class="sxs-lookup"><span data-stu-id="d9936-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="d9936-128">Nella casella **Ordine di visualizzazione**, inserire un numero che rappresenta l'rdine di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9936-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="d9936-129">Al termine dell'aggiunta delle dimensioni, selezionare **Salva** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d9936-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="d9936-130">L'immagine seguente mostra un esempio di un gruppo di dimensioni per "taglie di camicie casual".</span><span class="sxs-lookup"><span data-stu-id="d9936-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Creare un gruppo di dimensioni](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="d9936-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d9936-132">Additional resources</span></span>

[<span data-ttu-id="d9936-133">Panoramica delle informazioni sul prodotto</span><span class="sxs-lookup"><span data-stu-id="d9936-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="d9936-134">Configurare prodotti di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d9936-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="d9936-135">Dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="d9936-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)
