---
title: Modulo menu di spostamento
description: In questo argomento vengono descritti i moduli menu di spostamento per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 91239bd1db3f5819b7ad8d45ccfd8ab0d88b1b41
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817876"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="b09e5-103">Modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="b09e5-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="b09e5-104">In questo argomento vengono descritti i moduli menu di spostamento per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b09e5-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b09e5-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b09e5-105">Overview</span></span>

<span data-ttu-id="b09e5-106">Lo scopo principale dei moduli del menu di spostamento è quello di consentire agli utenti del sito di sfogliare i prodotti e le pagine del sito secondo la gerarchia di navigazione del canale definita in Dynamics 365 Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="b09e5-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="b09e5-107">Gli elementi configurati in un modulo del menu di spostamento vengono visualizzati come spostamento dell'intestazione del sito.</span><span class="sxs-lookup"><span data-stu-id="b09e5-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="b09e5-108">I moduli del menu di spostamento supportano anche voci di menu statiche che collegano ad altre pagine su un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="b09e5-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="b09e5-109">Il modulo del menu di spostamento può essere aggiunto al modulo dell'intestazione di una pagina.</span><span class="sxs-lookup"><span data-stu-id="b09e5-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="b09e5-110">Nel tema Fabrikam, il menu di spostamento mostra due livelli per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b09e5-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="b09e5-111">Nel tema Starter, il menu di spostamento mostra tre livelli per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b09e5-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="b09e5-112">Per passare al numero di livelli, è necessaria un'estensione di visualizzazione per il tema.</span><span class="sxs-lookup"><span data-stu-id="b09e5-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="b09e5-113">La figura seguente mostra un esempio di un menu di spostamento per il sito Fabrikam con due livelli di gerarchia di categorie e alcune voci di menu statiche.</span><span class="sxs-lookup"><span data-stu-id="b09e5-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="b09e5-114">![Esempio di modulo del menu di spostamento](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="b09e5-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="b09e5-115">Proprietà del modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="b09e5-115">Navigation menu module properties</span></span>

| <span data-ttu-id="b09e5-116">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="b09e5-116">Property name</span></span>             | <span data-ttu-id="b09e5-117">Valore</span><span class="sxs-lookup"><span data-stu-id="b09e5-117">Value</span></span>                 | <span data-ttu-id="b09e5-118">descrizione</span><span class="sxs-lookup"><span data-stu-id="b09e5-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="b09e5-119">Origine</span><span class="sxs-lookup"><span data-stu-id="b09e5-119">Source</span></span>                  | <span data-ttu-id="b09e5-120">**Vendita al dettaglio**, **Creazione manuale**, **Vendita al dettaglio e creazione manuale**</span><span class="sxs-lookup"><span data-stu-id="b09e5-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="b09e5-121">Il valore **Vendita al dettaglio** consente di visualizzare la gerarchia di spostamento del canale da Commerce headquarters nel menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="b09e5-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="b09e5-122">Il valore **Creazione manuale** consente di curare le voci di menu statiche.</span><span class="sxs-lookup"><span data-stu-id="b09e5-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="b09e5-123">Il valore **Vendita al dettaglio e creazione manuale** consente una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="b09e5-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="b09e5-124">Mostrare le immagini di categoria</span><span class="sxs-lookup"><span data-stu-id="b09e5-124">Show category images</span></span> | <span data-ttu-id="b09e5-125">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="b09e5-125">**True** or **False**</span></span>    | <span data-ttu-id="b09e5-126">Se abilitata, questa proprietà visualizza le immagini delle categorie nel menu di spostamento come definito in Commerce headquarters per ciascuna categoria.</span><span class="sxs-lookup"><span data-stu-id="b09e5-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="b09e5-127">Aggiunto nella versione Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="b09e5-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="b09e5-128">Voce di menu statico</span><span class="sxs-lookup"><span data-stu-id="b09e5-128">Static menu item</span></span>| <span data-ttu-id="b09e5-129">Matrice di valori</span><span class="sxs-lookup"><span data-stu-id="b09e5-129">Array of values</span></span>| <span data-ttu-id="b09e5-130">Voci di menu statico che associano il nome di una voce di menu a un collegamento di una pagina del sito statico.</span><span class="sxs-lookup"><span data-stu-id="b09e5-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="b09e5-131">È possibile creare voci di menu sotto altre voci di menu.</span><span class="sxs-lookup"><span data-stu-id="b09e5-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="b09e5-132">Per impostazione predefinita, i menu statici vengono visualizzati al livello radice e verranno aggiunti alla gerarchia di spostamento del canale, se esistente.</span><span class="sxs-lookup"><span data-stu-id="b09e5-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="b09e5-133">La figura seguente mostra un esempio di un'immagine di categoria visualizzata nel menu di spostamento per il sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="b09e5-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="b09e5-134">![Esempio di un modulo menu di spostamento con immagini di categorie](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="b09e5-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="b09e5-135">Aggiungere un modulo del menu di spostamento a un modulo di intestazione</span><span class="sxs-lookup"><span data-stu-id="b09e5-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="b09e5-136">Per dettagli su come aggiungere un modulo del menu di spostamento a un modulo di intestazione, vedere [Modulo di intestazione](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="b09e5-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b09e5-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b09e5-137">Additional resources</span></span>

[<span data-ttu-id="b09e5-138">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="b09e5-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b09e5-139">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="b09e5-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b09e5-140">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="b09e5-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="b09e5-141">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="b09e5-141">Header module</span></span>](author-header-module.md)
