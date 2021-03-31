---
title: Creare pagine di e-commerce dinamiche in base ai parametri URL
description: In questo argomento viene descritto come configurare una pagina di e-commerce Microsoft Dynamics 365 Commerce in grado di offrire contenuti dinamici, in base ai parametri URL.
author: StuHarg
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d6b4756fc81dc99786da251d5d9a575a71ccc49
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208017"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="4240e-103">Creare pagine di e-commerce dinamiche in base ai parametri URL</span><span class="sxs-lookup"><span data-stu-id="4240e-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="4240e-104">In questo argomento viene descritto come configurare una pagina di e-commerce Microsoft Dynamics 365 Commerce in grado di offrire contenuti dinamici, in base ai parametri URL.</span><span class="sxs-lookup"><span data-stu-id="4240e-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="4240e-105">Una pagina di e-commerce può essere configurata per offrire contenuti diversi, in base a un segmento nel percorso dell'URL.</span><span class="sxs-lookup"><span data-stu-id="4240e-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="4240e-106">Pertanto, la pagina è nota come pagina dinamica.</span><span class="sxs-lookup"><span data-stu-id="4240e-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="4240e-107">Il segmento viene utilizzato come parametro per recuperare il contenuto della pagina.</span><span class="sxs-lookup"><span data-stu-id="4240e-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="4240e-108">Ad esempio, una pagina denominata **blog\_viewer** viene creata e associata all'URL `https://fabrikam.com/blog`.</span><span class="sxs-lookup"><span data-stu-id="4240e-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="4240e-109">Questa pagina può quindi essere utilizzata per mostrare contenuti diversi, in base all'ultimo segmento nel percorso dell'URL.</span><span class="sxs-lookup"><span data-stu-id="4240e-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="4240e-110">Ad esempio, l'ultimo segmento nell'URL `https://fabrikam.com/blog/article-1` è **article-1**.</span><span class="sxs-lookup"><span data-stu-id="4240e-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="4240e-111">Le pagine personalizzate separate che sostituiscono la pagina dinamica possono anche essere associate a segmenti nel percorso dell'URL.</span><span class="sxs-lookup"><span data-stu-id="4240e-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="4240e-112">Ad esempio, una pagina denominata **blog\_summary** viene creata e associata all'URL `https://fabrikam.com/blog/about-this-blog`.</span><span class="sxs-lookup"><span data-stu-id="4240e-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="4240e-113">Quando viene richiesto questo URL, la pagina **blog\_summary** associata al parametro **/about-this-blog** viene restituita al posto della pagina **blog\_viewer**.</span><span class="sxs-lookup"><span data-stu-id="4240e-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="4240e-114">La funzionalità per l'hosting, il recupero e la visualizzazione del contenuto dinamico della pagina viene implementata utilizzando un modulo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4240e-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="4240e-115">Per ulteriori informazioni, vedi [Estendibilità del canale online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="4240e-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="4240e-116">Impostare una pagina di e-commerce dinamica</span><span class="sxs-lookup"><span data-stu-id="4240e-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="4240e-117">Per impostare una pagina di e-commerce dinamica, è necessario creare la pagina dinamica, creare l'URL di base e configurare il percorso della pagina dinamica.</span><span class="sxs-lookup"><span data-stu-id="4240e-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="4240e-118">Creare la pagina che offrirà il contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="4240e-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="4240e-119">Per creare una pagina che offrirà contenuto dinamico, segui i passaggi in [Aggiungere una nuova pagina del sito](add-new-page.md).</span><span class="sxs-lookup"><span data-stu-id="4240e-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="4240e-120">La pagina che creerai richiederà l'implementazione di un modulo che utilizza l'ultimo segmento nel percorso dell'URL per recuperare il contenuto da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="4240e-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="4240e-121">Per ulteriori informazioni sullo sviluppo di moduli personalizzati, vedi [Estendibilità del canale online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="4240e-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="4240e-122">Creare l'URL di base per la pagina dinamica</span><span class="sxs-lookup"><span data-stu-id="4240e-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="4240e-123">Per creare l'URL di base per la pagina dinamica in Creazione di siti di Commerce, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="4240e-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="4240e-124">Vai a **URL** e seleziona **Nuovo \> Nuovo URL**.</span><span class="sxs-lookup"><span data-stu-id="4240e-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="4240e-125">Nella finestra di dialogo **Crea nuovo URL**, seleziona **Pagina interna**.</span><span class="sxs-lookup"><span data-stu-id="4240e-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="4240e-126">In **Percorso URL**, immetti il percorso che servirà da radice per la pagina dinamica (in questo esempio, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="4240e-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="4240e-127">Quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4240e-127">Then select **Next**.</span></span>
1. <span data-ttu-id="4240e-128">Nella finestra di dialogo **Seleziona pagina**, seleziona la pagina creata come pagina dinamica, quindi seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4240e-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="4240e-129">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="4240e-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="4240e-130">Configurare il percorso della pagina dinamica</span><span class="sxs-lookup"><span data-stu-id="4240e-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="4240e-131">Per configurare il percorso della pagina dinamica in Creazione di siti di Commerce, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="4240e-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="4240e-132">Vai a **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="4240e-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="4240e-133">In **Percorsi URL con parametri**, seleziona **Aggiungi**, quindi immetti il percorso dell'URL immesso quando hai creato l'URL (in questo esempio, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="4240e-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="4240e-134">Seleziona **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="4240e-134">Select **Save and publish**.</span></span>

<span data-ttu-id="4240e-135">Dopo aver configurato il percorso, tutte le richieste del percorso dell'URL con parametri restituiranno la pagina associata a quell'URL.</span><span class="sxs-lookup"><span data-stu-id="4240e-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="4240e-136">Se le richieste contengono un segmento aggiuntivo, verrà restituita la pagina associata e il contenuto della pagina verrà recuperato utilizzando il segmento come parametro.</span><span class="sxs-lookup"><span data-stu-id="4240e-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="4240e-137">Per esempio, `https://fabrikam.com/blog/article-1` restituirà la pagina **blog\_summary** e il contenuto della pagina verrà recuperato utilizzando il parametro **/article-1**.</span><span class="sxs-lookup"><span data-stu-id="4240e-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="4240e-138">Sostituzione di un URL con parametri con una pagina personalizzata</span><span class="sxs-lookup"><span data-stu-id="4240e-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="4240e-139">Per sostituire un URL con parametri con una pagina personalizzata in Creazione di siti di Commerce, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="4240e-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="4240e-140">Vai a **URL** e seleziona **Nuovo \> Nuovo URL**.</span><span class="sxs-lookup"><span data-stu-id="4240e-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="4240e-141">Nella finestra di dialogo **Crea nuovo URL**, seleziona **Pagina interna**.</span><span class="sxs-lookup"><span data-stu-id="4240e-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="4240e-142">In **Percorso URL**, immetti il percorso che include il segmento da sostituire (in questo esempio, **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="4240e-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="4240e-143">Quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4240e-143">Then select **Next**.</span></span>
1. <span data-ttu-id="4240e-144">Nella finestra di dialogo **Seleziona pagina**, seleziona la pagina personalizzata e quindi seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4240e-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="4240e-145">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="4240e-145">Select **Publish**.</span></span>
1. <span data-ttu-id="4240e-146">Se la pagina personalizzata non è stata ancora pubblicata, vai a **Pagine**, seleziona la pagina personalizzata, quindi seleziona **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="4240e-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="4240e-147">Dopo la pubblicazione, la pagina personalizzata verrà offerta al posto della pagina dinamica con contenuto con parametri.</span><span class="sxs-lookup"><span data-stu-id="4240e-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4240e-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4240e-148">Additional resources</span></span>

[<span data-ttu-id="4240e-149">Modificare una pagina del sito esistente</span><span class="sxs-lookup"><span data-stu-id="4240e-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="4240e-150">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="4240e-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="4240e-151">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="4240e-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="4240e-152">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="4240e-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="4240e-153">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="4240e-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="4240e-154">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="4240e-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="4240e-155">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="4240e-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="4240e-156">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="4240e-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="4240e-157">Estendibilità del canale online</span><span class="sxs-lookup"><span data-stu-id="4240e-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]