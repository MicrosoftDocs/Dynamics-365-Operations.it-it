---
title: Panoramica della libreria moduli
description: Questo argomento fornisce una panoramica della libreria di moduli di Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76fd75c2ed9a3ba4728129b77a43b50267be3bf3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795335"
---
# <a name="module-library-overview"></a><span data-ttu-id="d977a-103">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="d977a-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d977a-104">Questo argomento fornisce una panoramica della libreria di moduli di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d977a-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

<span data-ttu-id="d977a-105">La libreria di moduli di Dynamics 365 Commerce è una raccolta di moduli che possono essere utilizzati per creare un sito Web di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="d977a-105">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="d977a-106">I moduli hanno aspetti di interfaccia utente e di comportamento funzionale.</span><span class="sxs-lookup"><span data-stu-id="d977a-106">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="d977a-107">Ai moduli nella libreria di moduli è possibile applicare dei temi per modificarne l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="d977a-107">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="d977a-108">I temi utilizzano Cascading Style Sheets (CSS).</span><span class="sxs-lookup"><span data-stu-id="d977a-108">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="d977a-109">Un tema per un sito di e-Commerce fittizio denominato "Fabrikam" è incluso nella libreria di moduli e può essere utilizzato come riferimento.</span><span class="sxs-lookup"><span data-stu-id="d977a-109">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="d977a-110">Moduli della libreria di moduli</span><span class="sxs-lookup"><span data-stu-id="d977a-110">Module library modules</span></span>

<span data-ttu-id="d977a-111">I seguenti tipi di moduli sono disponibili nella libreria di moduli:</span><span class="sxs-lookup"><span data-stu-id="d977a-111">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="d977a-112">**Modulo contenitore** - Un modulo contenitore è un modulo semplice che funge da host per altri moduli.</span><span class="sxs-lookup"><span data-stu-id="d977a-112">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="d977a-113">Controlla il layout dei moduli che contiene.</span><span class="sxs-lookup"><span data-stu-id="d977a-113">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="d977a-114">**Moduli Marketing** - I moduli Marketing includono moduli blocco di contenuto, blocchi di testo, lettore video e sequenza.</span><span class="sxs-lookup"><span data-stu-id="d977a-114">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="d977a-115">Tutti questi moduli possono essere utilizzati per presentare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="d977a-115">All these modules can be used to showcase content.</span></span> <span data-ttu-id="d977a-116">Sono utilizzabili in qualsiasi pagina e sono basati sui dati del sistema di gestione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="d977a-116">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="d977a-117">**Moduli Intestazione e Piè di pagina** - I moduli Intestazione e Piè di pagina sono visualizzati nell'intestazione e nel piè di pagina di tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="d977a-117">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="d977a-118">Questi moduli possono essere configurati come necessario mediante le proprietà.</span><span class="sxs-lookup"><span data-stu-id="d977a-118">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="d977a-119">**Moduli Ricerca** - I prodotti possono essere individuati utilizzando il modulo Ricerca nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="d977a-119">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="d977a-120">I risultati della ricerca sono visualizzati nella pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="d977a-120">Search results appear on the search results page.</span></span> <span data-ttu-id="d977a-121">I prodotti possono anche essere individuati nelle pagine delle categorie, ovvero pagine dedicate a ogni categoria supportata nella gerarchia di navigazione del canale.</span><span class="sxs-lookup"><span data-stu-id="d977a-121">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="d977a-122">Inoltre, i moduli Criterio di affinamento possono essere utilizzati per filtrare ulteriormente i risultati nelle ricerche e nelle pagine delle categorie.</span><span class="sxs-lookup"><span data-stu-id="d977a-122">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="d977a-123">**Moduli Pagina dettagli prodotto** - Le pagine dettagli prodotto utilizzano vari moduli per visualizzare le informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="d977a-123">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="d977a-124">Il modulo Casella acquisti consente ai clienti di visualizzare i prodotti e aggiungerli al carrello.</span><span class="sxs-lookup"><span data-stu-id="d977a-124">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="d977a-125">Altri moduli, come ad esempio il modulo Specifiche tecniche, visualizzano i dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d977a-125">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="d977a-126">Il modulo Valutazioni e recensioni può essere utilizzato per visualizzare e fornire recensioni.</span><span class="sxs-lookup"><span data-stu-id="d977a-126">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="d977a-127">**Modulo Acquista online e preleva nel punto vendita** - Il modulo Acquista online e preleva nel punto vendita è integrato in Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="d977a-127">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="d977a-128">Può essere utilizzato per individuare i punti vendita vicini dove i clienti possono prelevare i prodotti acquistati.</span><span class="sxs-lookup"><span data-stu-id="d977a-128">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="d977a-129">**Moduli Acquisto** - I moduli Acquisto includono il modulo Carrello, che può essere utilizzato per aggiungere articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="d977a-129">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="d977a-130">Il modulo Checkout acquisisce l'indirizzo di spedizione, le opzioni di consegna e informazioni su gift card, programma fedeltà e carta di credito, di modo che l'ordine possa essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="d977a-130">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="d977a-131">Dopo che un ordine viene passato, il modulo Conferma ordine può essere utilizzato per visualizzare i dettagli di conferma.</span><span class="sxs-lookup"><span data-stu-id="d977a-131">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="d977a-132">**Moduli Gestione account** - Il modulo Accesso consente ai clienti di accedere a un account esistente e il modulo Registrazione consente agli stessi di creare un nuovo account.</span><span class="sxs-lookup"><span data-stu-id="d977a-132">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="d977a-133">Dopo la creazione di un account, il modulo Storico ordini può essere utilizzato per visualizzare gli ultimi ordini e il modulo Dettagli ordine può essere utilizzato per visualizzare i dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="d977a-133">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="d977a-134">**Modulo Suggerimenti** - I suggerimenti sono visualizzati utilizzando il modulo Posizionamento prodotto.</span><span class="sxs-lookup"><span data-stu-id="d977a-134">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="d977a-135">Questo modulo supporta elenchi algoritmici e editoriali che possono essere visualizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="d977a-135">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d977a-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d977a-136">Additional resources</span></span>

[<span data-ttu-id="d977a-137">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="d977a-137">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d977a-138">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="d977a-138">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d977a-139">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="d977a-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d977a-140">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="d977a-140">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d977a-141">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="d977a-141">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="d977a-142">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="d977a-142">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="d977a-143">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="d977a-143">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]