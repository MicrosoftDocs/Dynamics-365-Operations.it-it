---
title: Modificare l'ordine di visualizzazione per entità di merchandising
description: In questo argomento vengono descritti i concetti correlati al controllo dell'ordine di visualizzazione per varie entità di merchandising in Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b983cb5c63db171c76d34375a93a2b9086185d3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023000"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="50d55-103">Modificare l'ordine di visualizzazione per entità di merchandising</span><span class="sxs-lookup"><span data-stu-id="50d55-103">Change the sort order for merchandising entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="50d55-104">Per i rivenditori, l'individuazione dei prodotti è uno strumento principale per l'interazione dei clienti in tutti i canali.</span><span class="sxs-lookup"><span data-stu-id="50d55-104">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span> <span data-ttu-id="50d55-105">Varie funzionalità possono consentire ai clienti di scoprire facilmente i prodotti.</span><span class="sxs-lookup"><span data-stu-id="50d55-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="50d55-106">Ad esempio, possono esaminare le categorie, cercare e filtrare.</span><span class="sxs-lookup"><span data-stu-id="50d55-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="50d55-107">In questo argomento vengono descritti i concetti correlati al controllo dell'ordine di visualizzazione per varie entità di merchandising.</span><span class="sxs-lookup"><span data-stu-id="50d55-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="50d55-108">Viene inoltre illustrato come modificare l'ordine di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="50d55-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="50d55-109">Panoramica</span><span class="sxs-lookup"><span data-stu-id="50d55-109">Overview</span></span>

<span data-ttu-id="50d55-110">Il supporto per ordinare varie entità di merchandising è stato migliorato.</span><span class="sxs-lookup"><span data-stu-id="50d55-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="50d55-111">Questo supporto è ora meglio allineato agli scenari per clienti esistenti che in precedenza richiedevano estensioni da partner di implementazione.</span><span class="sxs-lookup"><span data-stu-id="50d55-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="50d55-112">Nelle versioni di Retail precedenti alla versione 10.0.5, l'ordine delle categorie nella gerarchia di navigazione è alfabetico.</span><span class="sxs-lookup"><span data-stu-id="50d55-112">In versions of Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="50d55-113">La nuova funzionalità di ordinamento personalizzata consente ai responsabili del merchandising di configurare l'ordine per varie entità di merchandising in tutti i client dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="50d55-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="50d55-114">Questi client includono le sedi e i servizi clienti.</span><span class="sxs-lookup"><span data-stu-id="50d55-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a><span data-ttu-id="50d55-115">Configurare l'ordine di visualizzazione delle categorie nella gerarchia di prodotti</span><span class="sxs-lookup"><span data-stu-id="50d55-115">Configure the display order for categories in the product hierarchy</span></span>

<span data-ttu-id="50d55-116">Per poter completare questa procedura, i dati dimostrativi devono essere installati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="50d55-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="50d55-117">Selezionare **Retail e Commerce \> Prodotti e categorie \> Gerarchia di prodotti di Commerce**.</span><span class="sxs-lookup"><span data-stu-id="50d55-117">Go to **Retail and Commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
2. <span data-ttu-id="50d55-118">Fare clic su **Modifica gerarchia di categorie**.</span><span class="sxs-lookup"><span data-stu-id="50d55-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="50d55-119">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="50d55-119">Click **Edit**.</span></span>
4. <span data-ttu-id="50d55-120">Nella struttura espandere **TUTTO \> Sport d'azione**.</span><span class="sxs-lookup"><span data-stu-id="50d55-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="50d55-121">Nella struttura espandere **TUTTO \> Sport di squadra**.</span><span class="sxs-lookup"><span data-stu-id="50d55-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="50d55-122">Immettere un numero nel campo **Ordine di visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="50d55-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="50d55-123">(questo numero può essere negativo).</span><span class="sxs-lookup"><span data-stu-id="50d55-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="50d55-124">Ripetere i passaggi da 4 a 6 per tutte le categorie aggiuntive di cui si desidera modificare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="50d55-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="50d55-125">L'ordine di visualizzazione della gerarchia di navigazione nei canali verrà riflessa nella sede per la gerarchia di prodotti di Commerce e i prodotti rilasciati per categoria.</span><span class="sxs-lookup"><span data-stu-id="50d55-125">The display order for the channel navigation hierarchy will be reflected in HQ for the commerce product hierarchy and released products by category.</span></span>

![Gerarchia di prodotti ordinata con valori negativi](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Prodotti rilasciati per categoria ordinati in base alla gerarchia di prodotti](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="50d55-128">Configurare l'ordine di visualizzazione delle categorie nella gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="50d55-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="50d55-129">Per poter completare questa procedura, i dati dimostrativi devono essere installati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="50d55-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="50d55-130">Andare a **Retail e Commerce \> Prodotti e categorie \> Categorie di navigazione nei canali**.</span><span class="sxs-lookup"><span data-stu-id="50d55-130">Go to **Retail and Commerce \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="50d55-131">Nell'elenco, selezionare **Gerarchia di navigazione articoli di moda**.</span><span class="sxs-lookup"><span data-stu-id="50d55-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="50d55-132">Fare clic su **Modifica gerarchia di categorie**.</span><span class="sxs-lookup"><span data-stu-id="50d55-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="50d55-133">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="50d55-133">Click **Edit**.</span></span>
5. <span data-ttu-id="50d55-134">Nella struttura, selezionare **Abbigliamento \> Donna \> Scarpe**.</span><span class="sxs-lookup"><span data-stu-id="50d55-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="50d55-135">Immettere un numero nel campo **Ordine di visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="50d55-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="50d55-136">Nella struttura, selezionare **Abbigliamento \> Donna \> Top**.</span><span class="sxs-lookup"><span data-stu-id="50d55-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="50d55-137">Analogamente, è possibile definire l'ordine delle sottocategorie.</span><span class="sxs-lookup"><span data-stu-id="50d55-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="50d55-138">Nella struttura, selezionare **Abbigliamento \> Uomo \> Camicie casual**.</span><span class="sxs-lookup"><span data-stu-id="50d55-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="50d55-139">Immettere un numero nel campo **Ordine di visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="50d55-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="50d55-140">Nella struttura, selezionare **Abbigliamento \> Uomo \> Giacche e cappotti**.</span><span class="sxs-lookup"><span data-stu-id="50d55-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="50d55-141">Immettere un numero nel campo **Ordine di visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="50d55-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="50d55-142">Ripetere per tutte le altre categorie di cui si desidera modificare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="50d55-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="50d55-143">L'ordine di visualizzazione della gerarchia di navigazione nei canali è rispecchiato nella sede centrale, nel catalogo e nei canali.</span><span class="sxs-lookup"><span data-stu-id="50d55-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and channels.</span></span>

![Ordinamento personalizzato nella gerarchia di navigazione nei canali](./media/ChannelNavCustomSorted.png)

![Gerarchia di navigazione nei canali ordinata in base alla gerarchia di navigazione nei canali](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![POS con categorie ordinate](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="50d55-147">Per impostazione predefinita, la personalizzazione della funzionalità di ordinamento è disattivata.</span><span class="sxs-lookup"><span data-stu-id="50d55-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="50d55-148">Per informazioni su come attivare questa e altre funzionalità, vedere [Gestione funzionalità](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="50d55-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>