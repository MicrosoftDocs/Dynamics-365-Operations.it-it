---
title: Modulo menu di spostamento
description: In questo argomento vengono descritti i moduli menu di spostamento per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055739"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="bc7a3-103">Modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="bc7a3-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bc7a3-104">In questo argomento vengono descritti i moduli menu di spostamento per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bc7a3-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="bc7a3-105">Overview</span></span>

<span data-ttu-id="bc7a3-106">Lo scopo principale dei moduli del menu di spostamento è quello di consentire agli utenti del sito di sfogliare i prodotti e le pagine del sito secondo la gerarchia di navigazione del canale definita in Dynamics 365 Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="bc7a3-107">Gli elementi configurati in un modulo del menu di spostamento vengono visualizzati come spostamento dell'intestazione del sito.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="bc7a3-108">I moduli del menu di spostamento supportano anche voci di menu statiche che collegano ad altre pagine su un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="bc7a3-109">Il modulo del menu di spostamento può essere aggiunto al modulo dell'intestazione di una pagina.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="bc7a3-110">Nel tema Fabrikam, il menu di spostamento mostra due livelli per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="bc7a3-111">Nel tema Starter, il menu di spostamento mostra tre livelli per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="bc7a3-112">Per passare al numero di livelli, è necessaria un'estensione di visualizzazione per il tema.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="bc7a3-113">La figura seguente mostra un esempio di un menu di spostamento per il sito Fabrikam con due livelli di gerarchia di categorie e alcune voci di menu statiche.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="bc7a3-114">![Esempio di modulo del menu di spostamento](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="bc7a3-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="bc7a3-115">Proprietà del modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="bc7a3-115">Navigation menu module properties</span></span>

| <span data-ttu-id="bc7a3-116">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="bc7a3-116">Property name</span></span>             | <span data-ttu-id="bc7a3-117">Valore</span><span class="sxs-lookup"><span data-stu-id="bc7a3-117">Value</span></span>                 | <span data-ttu-id="bc7a3-118">descrizione</span><span class="sxs-lookup"><span data-stu-id="bc7a3-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="bc7a3-119">Origine</span><span class="sxs-lookup"><span data-stu-id="bc7a3-119">Source</span></span>                  | <span data-ttu-id="bc7a3-120">**Vendita al dettaglio** , **Creazione manuale** , **Vendita al dettaglio e creazione manuale**</span><span class="sxs-lookup"><span data-stu-id="bc7a3-120">**Retail** , **Manual authoring** , **Retail and manual authoring**</span></span> | <span data-ttu-id="bc7a3-121">Il valore **Vendita al dettaglio** consente di visualizzare la gerarchia di spostamento del canale da Commerce headquarters nel menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="bc7a3-122">Il valore **Creazione manuale** consente di curare le voci di menu statiche.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="bc7a3-123">Il valore **Vendita al dettaglio e creazione manuale** consente una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="bc7a3-124">Mostrare le immagini di categoria</span><span class="sxs-lookup"><span data-stu-id="bc7a3-124">Show category images</span></span> | <span data-ttu-id="bc7a3-125">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="bc7a3-125">**True** or **False**</span></span>    | <span data-ttu-id="bc7a3-126">Se abilitata, questa proprietà visualizza le immagini delle categorie nel menu di spostamento come definito in Commerce headquarters per ciascuna categoria.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="bc7a3-127">Aggiunto nella versione Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="bc7a3-128">Abilitare il menu di spostamento multilivello</span><span class="sxs-lookup"><span data-stu-id="bc7a3-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="bc7a3-129">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="bc7a3-129">**True** or **False**</span></span> | <span data-ttu-id="bc7a3-130">Quando questa proprietà è abilitata, il menu di spostamento può mostrare più livelli della gerarchia di spostamento.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="bc7a3-131">Questa funzionalità è disponibile nella versione 10.0.15 di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="bc7a3-132">Numero di livelli</span><span class="sxs-lookup"><span data-stu-id="bc7a3-132">Number of levels</span></span> | <span data-ttu-id="bc7a3-133">numero intero</span><span class="sxs-lookup"><span data-stu-id="bc7a3-133">integer</span></span> | <span data-ttu-id="bc7a3-134">Questa proprietà definisce il numero di livelli che devono essere visualizzati se la proprietà **Abilita menu di spostamento multilivello** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="bc7a3-135">Voce di menu statico</span><span class="sxs-lookup"><span data-stu-id="bc7a3-135">Static menu item</span></span>| <span data-ttu-id="bc7a3-136">Matrice di valori</span><span class="sxs-lookup"><span data-stu-id="bc7a3-136">Array of values</span></span>| <span data-ttu-id="bc7a3-137">Voci di menu statico che associano il nome di una voce di menu a un collegamento di una pagina del sito statico.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="bc7a3-138">È possibile creare voci di menu sotto altre voci di menu.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="bc7a3-139">Per impostazione predefinita, i menu statici vengono visualizzati al livello radice e verranno aggiunti alla gerarchia di spostamento del canale, se esistente.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="bc7a3-140">Mostra menu radice</span><span class="sxs-lookup"><span data-stu-id="bc7a3-140">Show root menu</span></span> | <span data-ttu-id="bc7a3-141">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="bc7a3-141">**True** or **False**</span></span> | <span data-ttu-id="bc7a3-142">Quando questa proprietà è abilitata, il menu di spostamento può essere definito in una radice personalizzata (ad esempio, **Acquista ora** ).</span><span class="sxs-lookup"><span data-stu-id="bc7a3-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now** ).</span></span> <span data-ttu-id="bc7a3-143">Questa funzionalità è disponibile nella versione 10.0.15 di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="bc7a3-144">Menu radice</span><span class="sxs-lookup"><span data-stu-id="bc7a3-144">Root menu</span></span> | <span data-ttu-id="bc7a3-145">stringa</span><span class="sxs-lookup"><span data-stu-id="bc7a3-145">string</span></span> | <span data-ttu-id="bc7a3-146">Questa proprietà può essere utilizzata per definire il testo per una radice personalizzata se la proprietà **Mostra menu radice** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="bc7a3-147">La figura seguente mostra un esempio di un'immagine di categoria visualizzata nel menu di spostamento per il sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="bc7a3-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="bc7a3-148">![Esempio di un modulo menu di spostamento con immagini di categorie](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="bc7a3-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="bc7a3-149">Aggiungere un modulo del menu di spostamento a un modulo di intestazione</span><span class="sxs-lookup"><span data-stu-id="bc7a3-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="bc7a3-150">Per dettagli su come aggiungere un modulo del menu di spostamento a un modulo di intestazione, vedere [Modulo di intestazione](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="bc7a3-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc7a3-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bc7a3-151">Additional resources</span></span>

[<span data-ttu-id="bc7a3-152">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="bc7a3-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bc7a3-153">Modulo percorso di navigazione</span><span class="sxs-lookup"><span data-stu-id="bc7a3-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="bc7a3-154">Modulo di selezione sito</span><span class="sxs-lookup"><span data-stu-id="bc7a3-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="bc7a3-155">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="bc7a3-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="bc7a3-156">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="bc7a3-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="bc7a3-157">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="bc7a3-157">Header module</span></span>](author-header-module.md)
