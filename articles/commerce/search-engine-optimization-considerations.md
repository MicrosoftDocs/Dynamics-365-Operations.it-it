---
title: Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito
description: In questo argomento vengono descritte le considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito dallo sviluppo alla produzione.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b35d0cb606e1b17a0258ea3fcb6287988d83091c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698213"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a><span data-ttu-id="ebcbb-103">Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito</span><span class="sxs-lookup"><span data-stu-id="ebcbb-103">Search engine optimization (SEO) considerations for your site</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ebcbb-104">In questo argomento vengono descritte le considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito dallo sviluppo alla produzione.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-104">This topic covers earch engine optimization (SEO) considerations for your site from development to production.</span></span>

## <a name="a-site-that-is-under-development"></a><span data-ttu-id="ebcbb-105">Sito in fase di sviluppo</span><span class="sxs-lookup"><span data-stu-id="ebcbb-105">A site that is under development</span></span>

<span data-ttu-id="ebcbb-106">Quando un sito è in fase di sviluppo, tutte le pagine del sito deve avere i tag **NOFOLLOW** e **NOINDEX**, di modo che i motori di ricerca non indicizzino le pagine e memorizzino le versioni di sviluppo del sito nella cache.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-106">While a site is under development, all site pages should have the **NOINDEX** and **NOFOLLOW** meta tags, so that search engines don't index the pages and store development versions of your site in their cache.</span></span> <span data-ttu-id="ebcbb-107">Per eseguire questa configurazione, è necessario aggiungere il modulo Tag meta predefinito al modello di pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-107">To do this configuration, you must add the default meta tags module to the site page template.</span></span> <span data-ttu-id="ebcbb-108">Le proprietà dei tag meta predefiniti saranno quindi disponibili nella sezione delle proprietà SEO nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-108">The default meta tags properties will then be available in the SEO properties section in the page editor.</span></span> <span data-ttu-id="ebcbb-109">È possibile utilizzare queste proprietà per gestire i tag meta.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-109">You can use these properties to manage the meta tags.</span></span>

## <a name="soft-launch-of-a-site"></a><span data-ttu-id="ebcbb-110">Soft launch di un sito</span><span class="sxs-lookup"><span data-stu-id="ebcbb-110">Soft launch of a site</span></span>

<span data-ttu-id="ebcbb-111">Durante un "soft launch", un sito Web è disponibile a un'audience o un mercato limitato prima che venga eseguito il full launch.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-111">During a "soft launch," a website is made available to a limited audience or market before the full launch occurs.</span></span> <span data-ttu-id="ebcbb-112">Se si esegue un soft launch del sito Web, è necessario prendere in considerazione la possibilità di mantenere i tag meta **NOINDEX**.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-112">If you do a soft launch of your website, you should consider leaving the **NOINDEX** meta tags in place.</span></span> <span data-ttu-id="ebcbb-113">In questo modo, il soft launch rimane disponibile solo per l'audience limitata a cui è destinato.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-113">In this way, you help guarantee that the soft launch remains restricted to the limited audience that you want to reach.</span></span>

## <a name="a-site-that-is-in-production"></a><span data-ttu-id="ebcbb-114">Sito in produzione</span><span class="sxs-lookup"><span data-stu-id="ebcbb-114">A site that is in production</span></span>

<span data-ttu-id="ebcbb-115">Quando un sito è in produzione, è necessario assicurarsi che tutte le pagine del sito siano contrassegnate correttamente.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-115">When a site is in production, you should make sure that all site pages are correctly tagged.</span></span> <span data-ttu-id="ebcbb-116">Microsoft Dynamics 365 Commerce utilizza le informazioni immesse per una pagina per eseguire il rendering di tutte le informazioni SEO in quella pagina.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-116">Microsoft Dynamics 365 Commerce uses the information that is entered for a page to render all the SEO information on that page.</span></span> <span data-ttu-id="ebcbb-117">I moduli seguenti forniscono queste funzionalità: riepilogo della pagina categoria, riepilogo della pagina elenco e riepilogo della pagina prodotto.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-117">The following modules provide this functionality: category page summary, list page summary, and product page summary.</span></span>

<span data-ttu-id="ebcbb-118">Per ottimizzare l'indicizzazione del motore di ricerca, il framework di rendering utilizza le informazioni delle proprietà SEO configurate in Dynamics 365 Commerce e le informazioni specifiche del modulo.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-118">To optimize search engine indexing, the rendering framework uses both information from the SEO properties that are configured in Dynamics 365 Commerce and module-specific information.</span></span> <span data-ttu-id="ebcbb-119">Per un sito in produzione, è necessario assicurarsi che il file robots.txt consenta l'indicizzazione dell'intero sito e contenga collegamenti al documento sulla mappa del sito pubblicato.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-119">For a site that is in production, you should make sure that the robots.txt file allows for indexing of your whole site, and that it contains links to your published site map document.</span></span> <span data-ttu-id="ebcbb-120">Attivare la funzionalità di generazione della mappa del sito in **Impostazioni sito \> Mappe del sito abilitate**.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-120">You should turn on the site map generation functionality at **Site Settings \> Site maps enabled**.</span></span>

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a><span data-ttu-id="ebcbb-121">Impostazioni SEO delle pagine per anteprima interna, audience limitata e tutte le audience</span><span class="sxs-lookup"><span data-stu-id="ebcbb-121">Page SEO settings for internal preview, limited audiences, and all audiences</span></span>

<span data-ttu-id="ebcbb-122">Poiché Dynamics 365 Commerce supporta le anteprime autenticate WYSIWYG, gli autori possono preparare il contenuto delle pagine senza preoccuparsi che le informazioni saranno visibili ai visitatori del sito.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-122">Because Dynamics 365 Commerce supports "what you see is what you get" (WYSIWYG) authenticated previews, authors can prepare their page content without having to worry that the information will become visible to site visitors.</span></span> <span data-ttu-id="ebcbb-123">Se è necessario pubblicare una pagina, ma l'esposizione deve essere limitata, deve avere il tag meta **NOINDEX**, di modo che non venga indicizzata dai motori di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-123">If a page must be published, but its exposure must be limited, it should have the **NOINDEX** meta tag, so that it won't be indexed by search engines.</span></span> <span data-ttu-id="ebcbb-124">Quindi, quando la pagina è pronta per tutte le audience, tutti i metadati SEO di base devono essere presenti, allo scopo di ottimizzare l'efficienza di indicizzazione dei motori di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-124">Then, when the page is ready for all audiences, all the basic SEO metadata should be present, to maximize the efficiency of search engine indexing.</span></span> <span data-ttu-id="ebcbb-125">Inoltre, il tag meta **NOLIMIT** deve essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="ebcbb-125">Additionally, the **NOLIMIT** meta tag should be removed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ebcbb-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ebcbb-126">Additional resources</span></span>

[<span data-ttu-id="ebcbb-127">Gestire utenti e ruoli di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="ebcbb-127">Manage e-Commerce users and roles</span></span>](manage-ecommerce-users-roles.md)

[<span data-ttu-id="ebcbb-128">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="ebcbb-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="ebcbb-129">Gestire i criteri di sicurezza del contenuto (CSP)</span><span class="sxs-lookup"><span data-stu-id="ebcbb-129">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
