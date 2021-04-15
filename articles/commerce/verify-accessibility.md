---
title: Verificare l'accessibilità del contenuto della pagina
description: Questo argomento descrive come verificare l'accessibilità del contenuto della pagina in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 885696c13b0e5353e6dbd9dc21cf075d5e301786
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791633"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="f4d74-103">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="f4d74-103">Verify page content accessibility</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f4d74-104">Questo argomento descrive come verificare l'accessibilità del contenuto della pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4d74-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f4d74-105">Al termine della modifica di una pagina, è necessario assicurarsi che il contenuto sia accessibile a tutti sul Web.</span><span class="sxs-lookup"><span data-stu-id="f4d74-105">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="f4d74-106">Negli strumenti di creazione di Commerce, è possibile verificare facilmente l'accessibilità del contenuto della pagina utilizzando il servizio [Microsoft Accessibility Insights](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="f4d74-106">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="f4d74-107">Questo servizio verifica il contenuto della tua pagina rispetto alle ultime linee guida sull'[accessibilità al World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="f4d74-107">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="f4d74-108">L'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) deve essere attivata a livello di tenant o di sito prima di poterla utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f4d74-108">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="f4d74-109">Attivare Microsoft Accessibility Insights per tutti i siti nel tuo tenant</span><span class="sxs-lookup"><span data-stu-id="f4d74-109">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="f4d74-110">Per attivare l'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) per tutti i siti Commerce nel tenant, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="f4d74-110">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="f4d74-111">Per accedere alle impostazioni del tenant, è necessario effettuare l'accesso a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f4d74-111">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="f4d74-112">Accedere a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f4d74-112">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="f4d74-113">Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="f4d74-113">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="f4d74-114">In **Impostazioni tenant**, selezionare **Funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-114">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="f4d74-115">Impostare l'opzione **Verifica accessibilità** su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-115">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="f4d74-116">Attivare Microsoft Accessibility Insights per un singolo sito</span><span class="sxs-lookup"><span data-stu-id="f4d74-116">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="f4d74-117">Per attivare l'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) per un singolo sito di Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="f4d74-117">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="f4d74-118">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="f4d74-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f4d74-119">Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="f4d74-119">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="f4d74-120">In **Impostazioni sito**, selezionare **Funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-120">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="f4d74-121">Impostare l'opzione **Verifica accessibilità** su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-121">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="f4d74-122">Verificare l'accessibilità del contenuto nella home page</span><span class="sxs-lookup"><span data-stu-id="f4d74-122">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="f4d74-123">Per utilizzare il servizio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrato per analizzare e verificare il contenuto della home page in Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="f4d74-123">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f4d74-124">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="f4d74-124">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f4d74-125">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-125">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="f4d74-126">Trovare e selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="f4d74-126">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="f4d74-127">Nella barra dei comandi, selezionare **Verifica accessibilità**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-127">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="f4d74-128">Viene visualizzata la pagina **Verifica accessibilità**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-128">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="f4d74-129">Al termine della scansione, rivedere il contenuto del report.</span><span class="sxs-lookup"><span data-stu-id="f4d74-129">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="f4d74-130">Se la verifica ha esito negativo, selezionare ciascun elemento della verifica non riuscito per espanderlo in modo da poter visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="f4d74-130">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="f4d74-131">Per chiudere il report dopo averlo esaminato, scorrere fino alla fine della pagina **Verifica accessibilità** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d74-131">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4d74-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f4d74-132">Additional resources</span></span>

[<span data-ttu-id="f4d74-133">Modificare una pagina del sito esistente</span><span class="sxs-lookup"><span data-stu-id="f4d74-133">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="f4d74-134">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="f4d74-134">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="f4d74-135">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="f4d74-135">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="f4d74-136">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="f4d74-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="f4d74-137">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="f4d74-137">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="f4d74-138">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="f4d74-138">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="f4d74-139">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="f4d74-139">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="f4d74-140">Creare pagine di e-commerce dinamiche in base ai parametri URL</span><span class="sxs-lookup"><span data-stu-id="f4d74-140">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
