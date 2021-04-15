---
title: Modulo Piè di pagina
description: In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d6e7b0ad4fe0723575a0ec55a9b02d110568db58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797235"
---
# <a name="footer-module"></a><span data-ttu-id="f9b91-103">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="f9b91-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="f9b91-104">In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f9b91-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f9b91-105">Il modulo Piè di pagina è un contenitore speciale utilizzato per l'hosting dei moduli visualizzati nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="f9b91-105">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="f9b91-106">Ad esempio, può includere collegamenti a varie pagine del sito, ad esempio le pagine **Politiche del punto vendita** e **Contattaci**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-106">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="f9b91-107">L'immagine seguente mostra un esempio di modulo Piè di pagina in una pagina di sito.</span><span class="sxs-lookup"><span data-stu-id="f9b91-107">The following image shows an example of a footer module on a site page.</span></span>

![Esempio di modulo Piè di pagina](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties&quot;></a><span data-ttu-id=&quot;f9b91-109&quot;>Proprietà del modulo Piè di pagina</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-109&quot;>Footer module properties</span></span> 

<span data-ttu-id=&quot;f9b91-110&quot;>Come la maggior parte dei contenitori, un modulo Piè di pagina supporta le proprietà per l'intestazione e la larghezza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-110&quot;>Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id=&quot;f9b91-111&quot;>Supporta inoltre l'aggiunta di molteplici moduli categoria Piè di pagina.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-111&quot;>It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id=&quot;f9b91-112&quot;>Per ogni modulo Categoria piè di pagina aggiunto viene eseguito il rendering come colonna nel modulo Piè di pagina.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-112&quot;>Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name=&quot;modules-available-in-a-footer-module&quot;></a><span data-ttu-id=&quot;f9b91-113&quot;>Moduli disponibili in un modulo Piè di pagina</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-113&quot;>Modules available in a footer module</span></span>

<span data-ttu-id=&quot;f9b91-114&quot;>**Elementi piè di pagina** - Un modulo Elementi piè di pagina può contenere un'intestazione, un'immagine e un collegamento.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-114&quot;>**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id=&quot;f9b91-115&quot;>L'intestazione può essere utilizzata da sola o in combinazione con un'immagine e un collegamento.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9b91-115&quot;>The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id=&quot;f9b91-116&quot;>Ogni collegamento nel piè di pagina può essere configurato di modo che abbia solo testo (ad esempio i collegamenti &quot;Contattaci&quot; e &quot;Privacy") oppure del testo e un'immagine (ad esempio collegamenti ai social media).</span><span class="sxs-lookup"><span data-stu-id="f9b91-116">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="f9b91-117">**Torna all'inizio** - Un modulo Torna all'inizio fornisce un collegamento per spostarsi rapidamente all'inizio della pagina.</span><span class="sxs-lookup"><span data-stu-id="f9b91-117">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="f9b91-118">È necessaria una destinazione.</span><span class="sxs-lookup"><span data-stu-id="f9b91-118">A destination is required.</span></span> <span data-ttu-id="f9b91-119">Il valore di destinazione predefinito è \#, che porta l'utente all'inizio della pagina.</span><span class="sxs-lookup"><span data-stu-id="f9b91-119">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="f9b91-120">Creare modulo piè di pagina</span><span class="sxs-lookup"><span data-stu-id="f9b91-120">Create a footer module</span></span>

1. <span data-ttu-id="f9b91-121">Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="f9b91-121">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="f9b91-122">Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-122">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f9b91-123">Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-123">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f9b91-124">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Categoria piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-124">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f9b91-125">Nello slot **Categoria piè di pagina** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-125">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f9b91-126">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-126">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f9b91-127">Selezionare lo slot **Elemento piè di pagina** e nel riquadro delle proprietà a destra, configurare l'intestazione, il collegamento, il testo del collegamento e l'immagine come necessario.</span><span class="sxs-lookup"><span data-stu-id="f9b91-127">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="f9b91-128">Per aggiungere ulteriori elementi piè di pagina, ripetere i passaggi da 5 a 7 per ognuno.</span><span class="sxs-lookup"><span data-stu-id="f9b91-128">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="f9b91-129">Per aggiungere un collegamento "torna all'inizio" al piè di pagina, selezionare i puntini di sospensione (**...**) nello slot **Categoria piè di pagina** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-129">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="f9b91-130">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Torna all'inizio** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9b91-130">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f9b91-131">Selezionare lo slot **Torna all'inizio** e nel riquadro delle proprietà a destra, configurare il testo e altre proprietà del modulo come necessario.</span><span class="sxs-lookup"><span data-stu-id="f9b91-131">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="f9b91-132">Selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="f9b91-132">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="f9b91-133">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="f9b91-133">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="f9b91-134">Nello slot **Piè di pagina** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.</span><span class="sxs-lookup"><span data-stu-id="f9b91-134">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="f9b91-135">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="f9b91-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="f9b91-136">Aggiungendo il frammento ai modelli di pagina, si assicura il rendering del piè di pagina in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="f9b91-136">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9b91-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f9b91-137">Additional resources</span></span>

[<span data-ttu-id="f9b91-138">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="f9b91-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f9b91-139">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="f9b91-139">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="f9b91-140">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="f9b91-140">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f9b91-141">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="f9b91-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f9b91-142">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="f9b91-142">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f9b91-143">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="f9b91-143">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f9b91-144">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="f9b91-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="f9b91-145">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="f9b91-145">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]