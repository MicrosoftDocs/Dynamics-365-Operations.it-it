---
title: Modulo Piè di pagina
description: In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697315"
---
# <a name="footer-module"></a><span data-ttu-id="27da0-103">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="27da0-103">Footer module</span></span>  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="27da0-104">In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="27da0-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="27da0-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="27da0-105">Overview</span></span>

<span data-ttu-id="27da0-106">Il modulo Piè di pagina è un contenitore speciale utilizzato per l'hosting dei moduli visualizzati nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="27da0-107">Ad esempio, può includere collegamenti a varie pagine del sito, ad esempio le pagine **Politiche del punto vendita** e **Contattaci**.</span><span class="sxs-lookup"><span data-stu-id="27da0-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="27da0-108">Proprietà del modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="27da0-108">Footer module properties</span></span> 

<span data-ttu-id="27da0-109">Come la maggior parte dei contenitori, un modulo Piè di pagina supporta le proprietà per l'intestazione e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="27da0-109">Like most containers, a footer module support properties for the heading and the width.</span></span> <span data-ttu-id="27da0-110">Supporta inoltre l'aggiunta di molteplici moduli categoria Piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="27da0-111">Per ogni modulo Categoria piè di pagina aggiunto viene eseguito il rendering come colonna nel modulo Piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="27da0-112">Moduli disponibili in un modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="27da0-112">Modules available in a footer module</span></span>

<span data-ttu-id="27da0-113">**Elementi piè di pagina** - Un modulo Elementi piè di pagina può contenere un'intestazione, un'immagine e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="27da0-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="27da0-114">L'intestazione può essere utilizzata da sola o in combinazione con un'immagine e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="27da0-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="27da0-115">Ogni collegamento nel piè di pagina può essere configurato di modo che abbia solo testo (ad esempio i collegamenti "Contattaci" e "Privacy") oppure del testo e un'immagine (ad esempio collegamenti ai social media).</span><span class="sxs-lookup"><span data-stu-id="27da0-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="27da0-116">**Torna all'inizio** - Un modulo Torna all'inizio fornisce un collegamento per spostarsi rapidamente all'inizio della pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="27da0-117">È necessaria una destinazione.</span><span class="sxs-lookup"><span data-stu-id="27da0-117">A destination is required.</span></span> <span data-ttu-id="27da0-118">Il valore di destinazione predefinito è #, che porta l'utente all'inizio della pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="27da0-119">Creare un modello piè di pagina</span><span class="sxs-lookup"><span data-stu-id="27da0-119">Author a footer module</span></span>

1. <span data-ttu-id="27da0-120">Nel pannello di navigazione, selezionare **Frammenti** e quindi **Nuovo frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="27da0-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="27da0-121">Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo Piè di pagina, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="27da0-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="27da0-122">Nell'albero a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) per il modulo Piè di pagina e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="27da0-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="27da0-123">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo Categoria piè di pagina e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="27da0-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="27da0-124">Nell'albero, selezionare il pulsante con i puntini di sospensione per il modulo Categoria piè di pagina e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="27da0-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="27da0-125">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo Elemento piè di pagina e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="27da0-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="27da0-126">Nell'albero, selezionare il modulo Elemento piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="27da0-127">Quindi, nel riquadro delle proprietà a destra, configurare l'intestazione, il collegamento, il testo del collegamento e l'immagine come necessario.</span><span class="sxs-lookup"><span data-stu-id="27da0-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="27da0-128">Per aggiungere ulteriori elementi piè di pagina, ripetere i passaggi da 5 a 7.</span><span class="sxs-lookup"><span data-stu-id="27da0-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="27da0-129">Per aggiungere un collegamento "torna all'inizio" al piè di pagina, selezionare il pulsante con i puntini di sospensione per il modulo Categoria piè di pagina e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="27da0-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="27da0-130">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo Torna all'inizio e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="27da0-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="27da0-131">Nell'albero, selezionare il modulo Torna all'inizio.</span><span class="sxs-lookup"><span data-stu-id="27da0-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="27da0-132">Quindi, nel riquadro delle proprietà a destra, configurare il modulo Torna all'inizio come necessario.</span><span class="sxs-lookup"><span data-stu-id="27da0-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="27da0-133">Salvare il frammento, archiviarlo e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="27da0-133">Save the page fragment, check it in, and publish it.</span></span>

<span data-ttu-id="27da0-134">In ogni modello di pagina creato per il sito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="27da0-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="27da0-135">Nello slot **Principale** della pagina predefinita, nel modulo Piè di pagina, aggiungere il frammento piè di pagina creato.</span><span class="sxs-lookup"><span data-stu-id="27da0-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="27da0-136">Salvare il modello, archiviarlo e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="27da0-136">Save the template, check it in, and publish it.</span></span>

<span data-ttu-id="27da0-137">Aggiungendo il frammento pagina ai modelli di pagina, si assicura il rendering del piè di pagina in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="27da0-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27da0-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="27da0-138">Additional resources</span></span>

[<span data-ttu-id="27da0-139">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="27da0-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="27da0-140">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="27da0-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="27da0-141">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="27da0-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="27da0-142">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="27da0-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="27da0-143">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="27da0-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="27da0-144">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="27da0-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="27da0-145">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="27da0-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="27da0-146">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="27da0-146">Footer module</span></span>](author-footer-module.md)
