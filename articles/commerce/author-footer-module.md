---
title: Modulo Piè di pagina
description: In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 16c9ca145aff97f0af242da4cf662367f1f4ca3d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211450"
---
# <a name="footer-module"></a><span data-ttu-id="d7f86-103">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="d7f86-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="d7f86-104">In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d7f86-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d7f86-105">Il modulo Piè di pagina è un contenitore speciale utilizzato per l'hosting dei moduli visualizzati nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="d7f86-105">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="d7f86-106">Ad esempio, può includere collegamenti a varie pagine del sito, ad esempio le pagine **Politiche del punto vendita** e **Contattaci**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-106">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="d7f86-107">L'immagine seguente mostra un esempio di modulo Piè di pagina in una pagina di sito.</span><span class="sxs-lookup"><span data-stu-id="d7f86-107">The following image shows an example of a footer module on a site page.</span></span>

![Esempio di modulo Piè di pagina](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="d7f86-109">Proprietà del modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="d7f86-109">Footer module properties</span></span> 

<span data-ttu-id="d7f86-110">Come la maggior parte dei contenitori, un modulo Piè di pagina supporta le proprietà per l'intestazione e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="d7f86-110">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="d7f86-111">Supporta inoltre l'aggiunta di molteplici moduli categoria Piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="d7f86-111">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="d7f86-112">Per ogni modulo Categoria piè di pagina aggiunto viene eseguito il rendering come colonna nel modulo Piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="d7f86-112">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="d7f86-113">Moduli disponibili in un modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="d7f86-113">Modules available in a footer module</span></span>

<span data-ttu-id="d7f86-114">**Elementi piè di pagina** - Un modulo Elementi piè di pagina può contenere un'intestazione, un'immagine e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="d7f86-114">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="d7f86-115">L'intestazione può essere utilizzata da sola o in combinazione con un'immagine e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="d7f86-115">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="d7f86-116">Ogni collegamento nel piè di pagina può essere configurato di modo che abbia solo testo (ad esempio i collegamenti "Contattaci" e "Privacy") oppure del testo e un'immagine (ad esempio collegamenti ai social media).</span><span class="sxs-lookup"><span data-stu-id="d7f86-116">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="d7f86-117">**Torna all'inizio** - Un modulo Torna all'inizio fornisce un collegamento per spostarsi rapidamente all'inizio della pagina.</span><span class="sxs-lookup"><span data-stu-id="d7f86-117">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="d7f86-118">È necessaria una destinazione.</span><span class="sxs-lookup"><span data-stu-id="d7f86-118">A destination is required.</span></span> <span data-ttu-id="d7f86-119">Il valore di destinazione predefinito è \#, che porta l'utente all'inizio della pagina.</span><span class="sxs-lookup"><span data-stu-id="d7f86-119">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="d7f86-120">Creare modulo piè di pagina</span><span class="sxs-lookup"><span data-stu-id="d7f86-120">Create a footer module</span></span>

1. <span data-ttu-id="d7f86-121">Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="d7f86-121">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="d7f86-122">Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-122">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="d7f86-123">Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-123">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d7f86-124">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Categoria piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-124">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d7f86-125">Nello slot **Categoria piè di pagina** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-125">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d7f86-126">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-126">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d7f86-127">Selezionare lo slot **Elemento piè di pagina** e nel riquadro delle proprietà a destra, configurare l'intestazione, il collegamento, il testo del collegamento e l'immagine come necessario.</span><span class="sxs-lookup"><span data-stu-id="d7f86-127">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="d7f86-128">Per aggiungere ulteriori elementi piè di pagina, ripetere i passaggi da 5 a 7 per ognuno.</span><span class="sxs-lookup"><span data-stu-id="d7f86-128">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="d7f86-129">Per aggiungere un collegamento "torna all'inizio" al piè di pagina, selezionare i puntini di sospensione (**...**) nello slot **Categoria piè di pagina** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-129">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="d7f86-130">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Torna all'inizio** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7f86-130">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d7f86-131">Selezionare lo slot **Torna all'inizio** e nel riquadro delle proprietà a destra, configurare il testo e altre proprietà del modulo come necessario.</span><span class="sxs-lookup"><span data-stu-id="d7f86-131">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="d7f86-132">Selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="d7f86-132">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="d7f86-133">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="d7f86-133">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="d7f86-134">Nello slot **Piè di pagina** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.</span><span class="sxs-lookup"><span data-stu-id="d7f86-134">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="d7f86-135">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="d7f86-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="d7f86-136">Aggiungendo il frammento ai modelli di pagina, si assicura il rendering del piè di pagina in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="d7f86-136">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7f86-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d7f86-137">Additional resources</span></span>

[<span data-ttu-id="d7f86-138">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="d7f86-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d7f86-139">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="d7f86-139">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d7f86-140">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="d7f86-140">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d7f86-141">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="d7f86-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d7f86-142">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="d7f86-142">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d7f86-143">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="d7f86-143">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="d7f86-144">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="d7f86-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="d7f86-145">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="d7f86-145">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]