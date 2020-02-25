---
title: Creare un URL di pagina
description: In questo argomento vengono descritti le procedure e i concetti di base per la creazione di un URL di pagina nel sito.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 588cbedb077fab0663d3d62fc4a8b8ed915635b3
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001923"
---
# <a name="create-a-page-url"></a><span data-ttu-id="3775b-103">Creare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="3775b-103">Create a page URL</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3775b-104">In questo argomento vengono descritti le procedure e i concetti di base per la creazione di un URL di pagina nel sito.</span><span class="sxs-lookup"><span data-stu-id="3775b-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

## <a name="overview"></a><span data-ttu-id="3775b-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="3775b-105">Overview</span></span>

<span data-ttu-id="3775b-106">L'URL completo, o assoluto, che punta a una pagina nel sito è costituito da più parti distinte.</span><span class="sxs-lookup"><span data-stu-id="3775b-106">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="3775b-107">Ad esempio, l'URL `https://www.contoso.com/en-us/contactus` include le seguenti parti:</span><span class="sxs-lookup"><span data-stu-id="3775b-107">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="3775b-108">`https://www.contoso.com` – Il protocollo HTTP e il dominio del sito.</span><span class="sxs-lookup"><span data-stu-id="3775b-108">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="3775b-109">`/en-us` – Il percorso della lingua del sito.</span><span class="sxs-lookup"><span data-stu-id="3775b-109">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="3775b-110">`/contactus` – L'URL relativo della pagina **Contattaci**.</span><span class="sxs-lookup"><span data-stu-id="3775b-110">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="3775b-111">Un URL relativo è anche denominato *slug* URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-111">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="3775b-112">L'utente stabilisce il dominio del sito e il percorso della lingua facoltativo del sito durante la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="3775b-112">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="3775b-113">È possibile aggiungere più domini e percorsi di lingua al sito mediante la pagina dei punti vendita online nelle impostazioni del sito.</span><span class="sxs-lookup"><span data-stu-id="3775b-113">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="3775b-114">Lo slug URL di una pagina esiste come entità autonoma nell'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="3775b-114">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="3775b-115">Un URL di pagina è composto da due parti: un nome che rappresenta lo slug URL e un puntatore a una pagina nel proprio sito o in un sito esterno.</span><span class="sxs-lookup"><span data-stu-id="3775b-115">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="3775b-116">Un URL di pagina può anche essere configurato per fungere da reindirizzamento a un'altra pagina nel proprio sito o in un sito esterno.</span><span class="sxs-lookup"><span data-stu-id="3775b-116">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="3775b-117">Creare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="3775b-117">Create a page URL</span></span>

<span data-ttu-id="3775b-118">È possibile creare URL di pagina in due modi:</span><span class="sxs-lookup"><span data-stu-id="3775b-118">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="3775b-119">Automaticamente, quando si crea una pagina.</span><span class="sxs-lookup"><span data-stu-id="3775b-119">Automatically, when you create a page</span></span>
- <span data-ttu-id="3775b-120">Manualmente, dalla pagina **URL**.</span><span class="sxs-lookup"><span data-stu-id="3775b-120">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="3775b-121">Creare un URL di pagina quando si crea una pagina</span><span class="sxs-lookup"><span data-stu-id="3775b-121">Create a page URL when you create a page</span></span>

<span data-ttu-id="3775b-122">Se si immette un nome nel campo **URL** quando si crea una nuova pagina, un URL di pagina che punta a quella pagina viene creato automaticamente nella pagina **URL**.</span><span class="sxs-lookup"><span data-stu-id="3775b-122">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="3775b-123">Dopo aver pubblicato l'URL e la pagina a cui punta, gli utenti del sito (i clienti) possono accedere alla pagina associata all'URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-123">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="3775b-124">Se si pubblica un URL senza pubblicare la pagina a cui punta, gli utenti del sito vedono un errore 404 quando tentano di accedere alla pagina.</span><span class="sxs-lookup"><span data-stu-id="3775b-124">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="3775b-125">Se si pubblica una pagina senza pubblicare l'URL che punta alla stessa, la pagina non è accessibile con un URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-125">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="3775b-126">Creare manualmente un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="3775b-126">Manually create a page URL</span></span>

<span data-ttu-id="3775b-127">Quando si creano nuove pagine, non è necessario specificare un URL di pagina.</span><span class="sxs-lookup"><span data-stu-id="3775b-127">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="3775b-128">Se si lascia vuoto il campo URL, la pagina viene creata in uno stato non collegato.</span><span class="sxs-lookup"><span data-stu-id="3775b-128">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="3775b-129">In questo caso, i clienti non potranno accedere alla pagina, anche se è stata pubblicata.</span><span class="sxs-lookup"><span data-stu-id="3775b-129">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="3775b-130">Per rendere la pagina accessibile, è necessario creare manualmente l'URL e collegarlo alla pagina.</span><span class="sxs-lookup"><span data-stu-id="3775b-130">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="3775b-131">Per creare manualmente l'URL per una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3775b-131">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="3775b-132">Nella pagina **URL**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3775b-132">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="3775b-133">Selezionare la pagina del sito da associare all'URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-133">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="3775b-134">Immettere lo slug URL e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3775b-134">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="3775b-135">A questo punto, l'URL è in stato bozza.</span><span class="sxs-lookup"><span data-stu-id="3775b-135">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="3775b-136">Deve essere pubblicato affinché gli utenti del sito possano accedere alla pagina associata.</span><span class="sxs-lookup"><span data-stu-id="3775b-136">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="3775b-137">Aggiornare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="3775b-137">Update a page URL</span></span>

<span data-ttu-id="3775b-138">Per aggiornare la pagina di destinazione di un URL di pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3775b-138">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="3775b-139">Nella pagina **URL**, selezionare l'URL da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="3775b-139">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="3775b-140">Nel riquadro delle proprietà a destra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al campo della pagina di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3775b-140">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="3775b-141">Nella finestra di dialogo, selezionare un'altra pagina e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="3775b-141">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="3775b-142">Salvare e pubblicare l'URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-142">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="3775b-143">Reindirizzare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="3775b-143">Redirect a page URL</span></span>

<span data-ttu-id="3775b-144">In alcuni casi, è possibile che si voglia visualizzare una pagina diversa quando i clienti richiedono un URL specifico.</span><span class="sxs-lookup"><span data-stu-id="3775b-144">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="3775b-145">In tali casi, l'approccio migliore e più semplice consiste in genere nel modificare la pagina a cui l'URL di pagina punta.</span><span class="sxs-lookup"><span data-stu-id="3775b-145">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="3775b-146">Tuttavia, si potrebbero avere motivi legittimi di utilizzare reindirizzamenti HTTP 301 o 3023 per reindirizzare le richieste di un URL a un URL differente.</span><span class="sxs-lookup"><span data-stu-id="3775b-146">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="3775b-147">Per reindirizzare un URL a un URL differente, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3775b-147">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="3775b-148">Nella pagina **URL**, selezionare l'URL da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="3775b-148">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="3775b-149">Nel riquadro delle proprietà a destra, selezionare **Reindirizza**.</span><span class="sxs-lookup"><span data-stu-id="3775b-149">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="3775b-150">Selezionare una destinazione per il reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="3775b-150">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="3775b-151">Per puntare a un'altra pagina nel sito, selezionare **URL interno**, selezionare il pulsante con i puntini di sospensione (**...**) e quindi selezionare l'URL a cui reindirizzare.</span><span class="sxs-lookup"><span data-stu-id="3775b-151">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="3775b-152">Per puntare a una pagina in un sito esterno, selezionare **URL esterno**, quindi immettere l'URL completo di quella pagina.</span><span class="sxs-lookup"><span data-stu-id="3775b-152">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="3775b-153">Assicurarsi di includere il protocollo.</span><span class="sxs-lookup"><span data-stu-id="3775b-153">Be sure to include the protocol.</span></span> <span data-ttu-id="3775b-154">Ad esempio, immettere `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="3775b-154">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="3775b-155">Se l'URL reindirizza già a un URL interno, è necessario selezionare **Cancella selezione** prima di poter immettere un URL esterno.</span><span class="sxs-lookup"><span data-stu-id="3775b-155">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="3775b-156">Selezionare un tipo di reindirizzamento:</span><span class="sxs-lookup"><span data-stu-id="3775b-156">Select a redirect type:</span></span>

    - <span data-ttu-id="3775b-157">**Reindirizzamento permanente (301)** - Selezionare questa opzione quando si sa che il contenuto viene spostato in permanenza e che l'URL precedente non verrà ripristinato.</span><span class="sxs-lookup"><span data-stu-id="3775b-157">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="3775b-158">I motori di ricerca assegneranno il valore di ottimizzazione del motore di ricerca dell'URL di reindirizzamento all'URL a cui si è reindirizzati e aggiorneranno il relativo record per visualizzare il nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-158">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="3775b-159">**Reindirizzamento temporaneo (302)** - Selezionare questa opzione per reindirizzare il traffico senza aggiornare i motori di ricerca.</span><span class="sxs-lookup"><span data-stu-id="3775b-159">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="3775b-160">Questo approccio è in genere utilizzato se il contenuto viene ripristinato rapidamente al relativo URL precedente.</span><span class="sxs-lookup"><span data-stu-id="3775b-160">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="3775b-161">Quando si è pronti per implementare il reindirizzamento, salvare e pubblicare l'URL.</span><span class="sxs-lookup"><span data-stu-id="3775b-161">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3775b-162">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3775b-162">Additional resources</span></span>

[<span data-ttu-id="3775b-163">Personalizzare la navigazione del sito</span><span class="sxs-lookup"><span data-stu-id="3775b-163">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="3775b-164">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="3775b-164">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="3775b-165">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="3775b-165">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="3775b-166">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="3775b-166">Add languages to your site</span></span>](add-languages-to-site.md)
