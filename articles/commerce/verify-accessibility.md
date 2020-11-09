---
title: Verificare l'accessibilità del contenuto della pagina
description: Questo argomento descrive come verificare l'accessibilità del contenuto della pagina in Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fc3dca673510e1636f497bb7d5c295bebe025677
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015105"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="f0e30-103">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="f0e30-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f0e30-104">Questo argomento descrive come verificare l'accessibilità del contenuto della pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0e30-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f0e30-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f0e30-105">Overview</span></span>

<span data-ttu-id="f0e30-106">Al termine della modifica di una pagina, è necessario assicurarsi che il contenuto sia accessibile a tutti sul Web.</span><span class="sxs-lookup"><span data-stu-id="f0e30-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="f0e30-107">Negli strumenti di creazione di Commerce, è possibile verificare facilmente l'accessibilità del contenuto della pagina utilizzando il servizio [Microsoft Accessibility Insights](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="f0e30-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="f0e30-108">Questo servizio verifica il contenuto della tua pagina rispetto alle ultime linee guida sull'[accessibilità al World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="f0e30-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="f0e30-109">L'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) deve essere attivata a livello di tenant o di sito prima di poterla utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f0e30-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="f0e30-110">Attivare Microsoft Accessibility Insights per tutti i siti nel tuo tenant</span><span class="sxs-lookup"><span data-stu-id="f0e30-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="f0e30-111">Per attivare l'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) per tutti i siti Commerce nel tenant, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="f0e30-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e30-112">Per accedere alle impostazioni del tenant, è necessario effettuare l'accesso a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f0e30-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="f0e30-113">Accedere a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f0e30-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="f0e30-114">Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="f0e30-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="f0e30-115">In **Impostazioni tenant** , selezionare **Funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-115">Under **Tenant Settings** , select **Features**.</span></span>
1. <span data-ttu-id="f0e30-116">Impostare l'opzione **Verifica accessibilità** su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="f0e30-117">Attivare Microsoft Accessibility Insights per un singolo sito</span><span class="sxs-lookup"><span data-stu-id="f0e30-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="f0e30-118">Per attivare l'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) per un singolo sito di Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="f0e30-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="f0e30-119">In **Siti** , selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="f0e30-119">Under **Sites** , select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f0e30-120">Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="f0e30-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="f0e30-121">In **Impostazioni sito** , selezionare **Funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-121">Under **Site Settings** , select **Features**.</span></span>
1. <span data-ttu-id="f0e30-122">Impostare l'opzione **Verifica accessibilità** su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="f0e30-123">Verificare l'accessibilità del contenuto nella home page</span><span class="sxs-lookup"><span data-stu-id="f0e30-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="f0e30-124">Per utilizzare il servizio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrato per analizzare e verificare il contenuto della home page in Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="f0e30-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f0e30-125">In **Siti** , selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="f0e30-125">Under **Sites** , select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f0e30-126">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="f0e30-127">Trovare e selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="f0e30-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="f0e30-128">Nella barra dei comandi, selezionare **Verifica accessibilità**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="f0e30-129">Viene visualizzata la pagina **Verifica accessibilità**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="f0e30-130">Al termine della scansione, rivedere il contenuto del report.</span><span class="sxs-lookup"><span data-stu-id="f0e30-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="f0e30-131">Se la verifica ha esito negativo, selezionare ciascun elemento della verifica non riuscito per espanderlo in modo da poter visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="f0e30-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="f0e30-132">Per chiudere il report dopo averlo esaminato, scorrere fino alla fine della pagina **Verifica accessibilità** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0e30-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0e30-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f0e30-133">Additional resources</span></span>

[<span data-ttu-id="f0e30-134">Modificare una pagina del sito esistente</span><span class="sxs-lookup"><span data-stu-id="f0e30-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="f0e30-135">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="f0e30-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="f0e30-136">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="f0e30-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="f0e30-137">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="f0e30-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="f0e30-138">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="f0e30-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="f0e30-139">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="f0e30-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="f0e30-140">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="f0e30-140">Enrich a category landing page</span></span>](enrich-category-page.md)
