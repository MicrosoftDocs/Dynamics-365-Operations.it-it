---
title: Modulo Condivisione social
description: In questo argomento vengono descritti i moduli condivisione social e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 0fd81aa1f4b1358528f0135c1334dc7b4ac4461f
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761401"
---
# <a name="social-share-module"></a><span data-ttu-id="c823e-103">Modulo Condivisione social</span><span class="sxs-lookup"><span data-stu-id="c823e-103">Social share module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c823e-104">In questo argomento vengono descritti i moduli condivisione social e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c823e-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c823e-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c823e-105">Overview</span></span>

<span data-ttu-id="c823e-106">I moduli di condivisione social consentono agli utenti di condividere gli URL delle pagine del sito di e-commerce sui social media come Facebook, Twitter, Pinterest e LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="c823e-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="c823e-107">Gli URL delle pagine del sito possono essere condivisi anche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c823e-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="c823e-108">I moduli di condivisione social sono comunemente utilizzati nelle pagine dei dettagli del prodotto (PDP) per aiutare gli utenti a condividere le informazioni sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="c823e-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="c823e-109">Ogni modulo di condivisione social è un contenitore per moduli di articoli di condivisione social.</span><span class="sxs-lookup"><span data-stu-id="c823e-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="c823e-110">Ogni modulo di articolo di condivisione social può essere configurato per puntare a un sito di social media specifico.</span><span class="sxs-lookup"><span data-stu-id="c823e-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="c823e-111">Integrazione con Facebook, Twitter, Pinterest, LinkedIn e la posta elettronica sono supportati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c823e-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="c823e-112">Quando un utente del sito seleziona un simbolo di social media, viene avviato un iframe HTML per il rispettivo sito di social media.</span><span class="sxs-lookup"><span data-stu-id="c823e-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="c823e-113">All'interno dell'iframe, l'utente può accedere e pubblicare il contenuto della pagina che stava visualizzando.</span><span class="sxs-lookup"><span data-stu-id="c823e-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="c823e-114">Ogni piattaforma di social media può tenere traccia dei cookie, quindi questo modulo richiede agli utenti del sito di accettare il messaggio di notifica del consenso ai cookie.</span><span class="sxs-lookup"><span data-stu-id="c823e-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="c823e-115">Quando il consenso ai cookie non viene accettato, il modulo verrà nascosto nella pagina.</span><span class="sxs-lookup"><span data-stu-id="c823e-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="c823e-116">Per ulteriori informazioni vedere [Conformità dei cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="c823e-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="c823e-117">La seguente illustrazione evidenzia un esempio di un modulo di condivisione social utilizzato in una pagina dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c823e-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Esempio di modulo di condivisione social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="c823e-119">Proprietà del modulo di condivisione social</span><span class="sxs-lookup"><span data-stu-id="c823e-119">Social share module properties</span></span>

| <span data-ttu-id="c823e-120">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c823e-120">Property name</span></span>             | <span data-ttu-id="c823e-121">Valore</span><span class="sxs-lookup"><span data-stu-id="c823e-121">Value</span></span>                 | <span data-ttu-id="c823e-122">descrizione</span><span class="sxs-lookup"><span data-stu-id="c823e-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="c823e-123">Titolo</span><span class="sxs-lookup"><span data-stu-id="c823e-123">Caption</span></span>                  | <span data-ttu-id="c823e-124">Testo</span><span class="sxs-lookup"><span data-stu-id="c823e-124">Text</span></span> | <span data-ttu-id="c823e-125">Questa proprietà specifica una didascalia per il modulo.</span><span class="sxs-lookup"><span data-stu-id="c823e-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="c823e-126">Orientamento</span><span class="sxs-lookup"><span data-stu-id="c823e-126">Orientation</span></span> | <span data-ttu-id="c823e-127">**Verticale** o **Orizzontale**</span><span class="sxs-lookup"><span data-stu-id="c823e-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="c823e-128">Questa proprietà definisce l'orientamento del layout per gli elementi dei social media.</span><span class="sxs-lookup"><span data-stu-id="c823e-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="c823e-129">Proprietà del modulo articoli di condivisione social</span><span class="sxs-lookup"><span data-stu-id="c823e-129">Social share item module properties</span></span>
| <span data-ttu-id="c823e-130">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c823e-130">Property name</span></span>             | <span data-ttu-id="c823e-131">Valore</span><span class="sxs-lookup"><span data-stu-id="c823e-131">Value</span></span>                 | <span data-ttu-id="c823e-132">descrizione</span><span class="sxs-lookup"><span data-stu-id="c823e-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="c823e-133">Social media</span><span class="sxs-lookup"><span data-stu-id="c823e-133">Social media</span></span>              | <span data-ttu-id="c823e-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span><span class="sxs-lookup"><span data-stu-id="c823e-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="c823e-135">Un menu a discesa con un elenco di piattaforme di social media.</span><span class="sxs-lookup"><span data-stu-id="c823e-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="c823e-136">Icona</span><span class="sxs-lookup"><span data-stu-id="c823e-136">Icon</span></span> |<span data-ttu-id="c823e-137">Immagine</span><span class="sxs-lookup"><span data-stu-id="c823e-137">Image</span></span>    | <span data-ttu-id="c823e-138">Questa sarà l'immagine che verrà mostrata per i rispettivi social media.</span><span class="sxs-lookup"><span data-stu-id="c823e-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="c823e-139">Come procedura consigliata, fare riferimento all'SDK della piattaforma di social media per l'immagine consigliata da utilizzare per ciascuna piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c823e-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="c823e-140">Aggiungere un modulo di condivisione social al modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="c823e-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="c823e-141">Per aggiungere un modulo di condivisione social al modulo casella acquisti, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c823e-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="c823e-142">Nel sito Fabrikam selezionare **Pagine**, quindi selezionare la pagina **DefaultPDP** per aprire la pagina dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c823e-142">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="c823e-143">Nello slot **Buybox (richiesto)** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="c823e-143">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c823e-144">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Condivisione social** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c823e-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c823e-145">Nello slot **Condivisione social** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="c823e-145">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c823e-146">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **SocialShare** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c823e-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c823e-147">Nel riquadro delle proprietà del modulo **SocialShare**, sotto **Orientamento**, selezionare **Orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="c823e-147">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="c823e-148">Aggiungere una didascalia secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="c823e-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="c823e-149">Nello slot **SocialShare** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="c823e-149">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c823e-150">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **SocialShareItem** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c823e-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c823e-151">Nel riquadro delle proprietà del modulo **SocialShareItem** sotto **Social media**, selezionare **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="c823e-151">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="c823e-152">Nel riquadro delle proprietà del modulo **SocialShareItem** sotto **Icona**, selezionare **+ Aggiungi immagine**.</span><span class="sxs-lookup"><span data-stu-id="c823e-152">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="c823e-153">Nella finestra di dialogo **Selettore multimediale** selezionare l'immagine del logo Facebook e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="c823e-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="c823e-154">Se nessuna immagine del logo Facebook è presente, selezionare **Carica un nuovo elemento multimediale** per caricarne una.</span><span class="sxs-lookup"><span data-stu-id="c823e-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="c823e-155">Aggiungere e configurare altri moduli **SocialShareItem** secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="c823e-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="c823e-156">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="c823e-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="c823e-157">La pagina mostrerà il modulo di condivisione social.</span><span class="sxs-lookup"><span data-stu-id="c823e-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="c823e-158">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="c823e-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c823e-159">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c823e-159">Additional resources</span></span>

[<span data-ttu-id="c823e-160">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="c823e-160">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c823e-161">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="c823e-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c823e-162">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="c823e-162">Cookie compliance</span></span>](cookie-compliance.md)
