---
title: Modulo Condivisione social
description: In questo argomento vengono descritti i moduli condivisione social e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82a8795360f453cdee19fa6e9e376a42e8276849
ms.sourcegitcommit: 69075e001d1fb4ef69282667052cd8d082273094
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022080"
---
# <a name="social-share-module"></a><span data-ttu-id="cf60b-103">Modulo Condivisione social</span><span class="sxs-lookup"><span data-stu-id="cf60b-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cf60b-104">In questo argomento vengono descritti i moduli condivisione social e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cf60b-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cf60b-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf60b-105">Overview</span></span>

<span data-ttu-id="cf60b-106">I moduli di condivisione social consentono agli utenti di condividere gli URL delle pagine del sito di e-commerce sui social media come Facebook, Twitter, Pinterest e LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="cf60b-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="cf60b-107">Gli URL delle pagine del sito possono essere condivisi anche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cf60b-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="cf60b-108">I moduli di condivisione social sono comunemente utilizzati nelle pagine dei dettagli del prodotto (PDP) per aiutare gli utenti a condividere le informazioni sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="cf60b-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="cf60b-109">Ogni modulo di condivisione social è un contenitore per moduli di articoli di condivisione social.</span><span class="sxs-lookup"><span data-stu-id="cf60b-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="cf60b-110">Ogni modulo di articolo di condivisione social può essere configurato per puntare a un sito di social media specifico.</span><span class="sxs-lookup"><span data-stu-id="cf60b-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="cf60b-111">Integrazione con Facebook, Twitter, Pinterest, LinkedIn e la posta elettronica sono supportati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cf60b-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="cf60b-112">Quando un utente del sito seleziona un simbolo di social media, viene avviato un iframe HTML per il rispettivo sito di social media.</span><span class="sxs-lookup"><span data-stu-id="cf60b-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="cf60b-113">All'interno dell'iframe, l'utente può accedere e pubblicare il contenuto della pagina che stava visualizzando.</span><span class="sxs-lookup"><span data-stu-id="cf60b-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="cf60b-114">Ogni piattaforma di social media può tenere traccia dei cookie, quindi questo modulo richiede agli utenti del sito di accettare il messaggio di notifica del consenso ai cookie.</span><span class="sxs-lookup"><span data-stu-id="cf60b-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="cf60b-115">Quando il consenso ai cookie non viene accettato, il modulo verrà nascosto nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cf60b-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="cf60b-116">Per ulteriori informazioni vedere [Conformità dei cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="cf60b-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="cf60b-117">La seguente illustrazione evidenzia un esempio di un modulo di condivisione social utilizzato in una pagina dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf60b-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Esempio di modulo di condivisione social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="cf60b-119">Proprietà del modulo di condivisione social</span><span class="sxs-lookup"><span data-stu-id="cf60b-119">Social share module properties</span></span>

| <span data-ttu-id="cf60b-120">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="cf60b-120">Property name</span></span>             | <span data-ttu-id="cf60b-121">Valore</span><span class="sxs-lookup"><span data-stu-id="cf60b-121">Value</span></span>                 | <span data-ttu-id="cf60b-122">descrizione</span><span class="sxs-lookup"><span data-stu-id="cf60b-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="cf60b-123">Titolo</span><span class="sxs-lookup"><span data-stu-id="cf60b-123">Caption</span></span>                  | <span data-ttu-id="cf60b-124">Testo</span><span class="sxs-lookup"><span data-stu-id="cf60b-124">Text</span></span> | <span data-ttu-id="cf60b-125">Questa proprietà specifica una didascalia per il modulo.</span><span class="sxs-lookup"><span data-stu-id="cf60b-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="cf60b-126">Orientamento</span><span class="sxs-lookup"><span data-stu-id="cf60b-126">Orientation</span></span> | <span data-ttu-id="cf60b-127">**Verticale** o **Orizzontale**</span><span class="sxs-lookup"><span data-stu-id="cf60b-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="cf60b-128">Questa proprietà definisce l'orientamento del layout per gli elementi dei social media.</span><span class="sxs-lookup"><span data-stu-id="cf60b-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="cf60b-129">Proprietà del modulo articoli di condivisione social</span><span class="sxs-lookup"><span data-stu-id="cf60b-129">Social share item module properties</span></span>
| <span data-ttu-id="cf60b-130">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="cf60b-130">Property name</span></span>             | <span data-ttu-id="cf60b-131">Valore</span><span class="sxs-lookup"><span data-stu-id="cf60b-131">Value</span></span>                 | <span data-ttu-id="cf60b-132">descrizione</span><span class="sxs-lookup"><span data-stu-id="cf60b-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="cf60b-133">Social media</span><span class="sxs-lookup"><span data-stu-id="cf60b-133">Social media</span></span>              | <span data-ttu-id="cf60b-134">**Facebook** , **Twitter** , **Pinterest** , **LinkedIn** , **Mail**</span><span class="sxs-lookup"><span data-stu-id="cf60b-134">**Facebook** , **Twitter** , **Pinterest** , **LinkedIn** , **Mail**</span></span> | <span data-ttu-id="cf60b-135">Un menu a discesa con un elenco di piattaforme di social media.</span><span class="sxs-lookup"><span data-stu-id="cf60b-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="cf60b-136">Icona</span><span class="sxs-lookup"><span data-stu-id="cf60b-136">Icon</span></span> |<span data-ttu-id="cf60b-137">Immagine</span><span class="sxs-lookup"><span data-stu-id="cf60b-137">Image</span></span>    | <span data-ttu-id="cf60b-138">Questa sarà l'immagine che verrà mostrata per i rispettivi social media.</span><span class="sxs-lookup"><span data-stu-id="cf60b-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="cf60b-139">Come procedura consigliata, fare riferimento all'SDK della piattaforma di social media per l'immagine consigliata da utilizzare per ciascuna piattaforma.</span><span class="sxs-lookup"><span data-stu-id="cf60b-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="cf60b-140">Aggiungere un modulo di condivisione social al modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="cf60b-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="cf60b-141">Per aggiungere un modulo di condivisione social al modulo casella acquisti, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="cf60b-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="cf60b-142">Nel sito Fabrikam selezionare **Pagine** , quindi selezionare la pagina **DefaultPDP** per aprire la pagina dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf60b-142">In the Fabrikam site, select **Pages** , and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="cf60b-143">Nello slot **Buybox (richiesto)** selezionare i puntini di sospensione ( **...** ), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-143">In the **Buybox (required)** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cf60b-144">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Condivisione social** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cf60b-145">Nello slot **Condivisione social** seleziona i puntini di sospensione ( **...** ), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-145">In the **Social Share** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cf60b-146">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **SocialShare** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cf60b-147">Nel riquadro delle proprietà del modulo **SocialShare** , sotto **Orientamento** , selezionare **Orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-147">In the properties pane of the **SocialShare** module, under **Orientation** , select **Horizontal**.</span></span> <span data-ttu-id="cf60b-148">Aggiungere una didascalia secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="cf60b-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="cf60b-149">Nello slot **SocialShare** seleziona i puntini di sospensione ( **...** ), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-149">In the **SocialShare** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cf60b-150">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **SocialShareItem** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cf60b-151">Nel riquadro delle proprietà del modulo **SocialShareItem** sotto **Social media** , selezionare **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-151">In the properties pane of the **SocialShareItem** module, under **Social Media** , select **Facebook**.</span></span>
1. <span data-ttu-id="cf60b-152">Nel riquadro delle proprietà del modulo **SocialShareItem** sotto **Icona** , selezionare **+ Aggiungi immagine**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-152">In the properties pane of the **SocialShareItem** module, under **Icon** , select **+ Add an image**.</span></span>
1. <span data-ttu-id="cf60b-153">Nella finestra di dialogo **Selettore multimediale** selezionare l'immagine del logo Facebook e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf60b-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="cf60b-154">Se nessuna immagine del logo Facebook è presente, selezionare **Carica un nuovo elemento multimediale** per caricarne una.</span><span class="sxs-lookup"><span data-stu-id="cf60b-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="cf60b-155">Aggiungere e configurare altri moduli **SocialShareItem** secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="cf60b-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="cf60b-156">Selezionare **Salva** , quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="cf60b-156">Select **Save** , and then select **Preview** to preview the page.</span></span> <span data-ttu-id="cf60b-157">La pagina mostrerà il modulo di condivisione social.</span><span class="sxs-lookup"><span data-stu-id="cf60b-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="cf60b-158">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="cf60b-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf60b-159">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cf60b-159">Additional resources</span></span>

[<span data-ttu-id="cf60b-160">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="cf60b-160">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="cf60b-161">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="cf60b-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="cf60b-162">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="cf60b-162">Cookie compliance</span></span>](cookie-compliance.md)
