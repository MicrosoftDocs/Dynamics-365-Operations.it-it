---
title: Modulo consenso per i cookie
description: In questo argomento vengono descritti i moduli consenso per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 60ce530575841c22355e4a14e8b0bbec6c0e35ab
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817284"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="4bb3d-103">Modulo consenso per i cookie</span><span class="sxs-lookup"><span data-stu-id="4bb3d-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4bb3d-104">In questo argomento vengono descritti i moduli consenso per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4bb3d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4bb3d-105">Overview</span></span>

<span data-ttu-id="4bb3d-106">Il modulo consenso per i cookie richiede agli utenti del sito di fornire esplicitamente il consenso per consentire i cookie per qualsiasi funzionalità o modulo che tiene traccia dei cookie del browser.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-106">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="4bb3d-107">Il consenso è richiesto la prima volta che un utente del sito apre un sito in una nuova sessione del browser.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-107">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="4bb3d-108">Una volta ricevuto il consenso, viene tracciato e all'utente del sito non verrà chiesto nuovamente il consenso.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-108">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="4bb3d-109">Per ulteriori informazioni vedere [Conformità dei cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4bb3d-109">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="4bb3d-110">Se non si riceve il consenso per i cookie dell'utente del sito, eventuali funzionalità o moduli che richiedono il consenso per i cookie non verranno visualizzati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-110">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="4bb3d-111">Ad esempio, il modulo checkout, il modulo condivisione social e la funzione di negozio preferito richiedono tutti il consenso dei cookie e non verranno visualizzati se non viene ricevuto il consenso dell'utente del sito.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-111">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="4bb3d-112">Un modulo consenso per i cookie può essere configurato nel frammento di intestazione della pagina in modo che possa essere applicato al caricamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-112">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="4bb3d-113">Il modulo consenso per i cookie deve includere un messaggio chiaro che informa l'utente del sito sull'utilizzo dei cookie nel sito e fornire un collegamento alla pagina sulla privacy del sito.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-113">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="4bb3d-114">La figura seguente evidenzia un esempio di messaggio di consenso per i cookie con un collegamento alla pagina dell'informativa sulla privacy del sito visualizzata nell'intestazione di una pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-114">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="4bb3d-115">![Esempio di modulo consenso per i cookie](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="4bb3d-115">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="4bb3d-116">Proprietà del modulo consenso per i cookie</span><span class="sxs-lookup"><span data-stu-id="4bb3d-116">Cookie consent module properties</span></span>

| <span data-ttu-id="4bb3d-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="4bb3d-117">Property name</span></span>             | <span data-ttu-id="4bb3d-118">Valore</span><span class="sxs-lookup"><span data-stu-id="4bb3d-118">Value</span></span>                 | <span data-ttu-id="4bb3d-119">descrizione</span><span class="sxs-lookup"><span data-stu-id="4bb3d-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="4bb3d-120">RTF</span><span class="sxs-lookup"><span data-stu-id="4bb3d-120">Rich Text</span></span>                  | <span data-ttu-id="4bb3d-121">RTF</span><span class="sxs-lookup"><span data-stu-id="4bb3d-121">Rich Text</span></span> | <span data-ttu-id="4bb3d-122">Specifica una notifica RTF per gli utenti del sito indicante che il sito utilizza i cookie del browser e che gli utenti devono accettare l'uso dei cookie affinché il sito sia completamente funzionale.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-122">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="4bb3d-123">Collegamenti</span><span class="sxs-lookup"><span data-stu-id="4bb3d-123">Links</span></span> | <span data-ttu-id="4bb3d-124">URL</span><span class="sxs-lookup"><span data-stu-id="4bb3d-124">URL</span></span> | <span data-ttu-id="4bb3d-125">È possibile aggiungere uno o più collegamenti alla pagina sulla privacy di un sito che descrive i tipi di cookie tracciati nel sito.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-125">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="4bb3d-126">Aggiungere un modulo consenso per i cookie alle pagine del sito</span><span class="sxs-lookup"><span data-stu-id="4bb3d-126">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="4bb3d-127">Per aggiungere in modo efficiente un modulo consenso per i cookie a più pagine del sito, è possibile aggiungerlo a un frammento di intestazione di pagina condivisa.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-127">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="4bb3d-128">Dopo che il frammento di intestazione è stato aggiunto a tutte le pagine del sito, verrà automaticamente visualizzata una notifica di consenso per i cookie la prima volta che un utente del sito accede a qualsiasi pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="4bb3d-128">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="4bb3d-129">Per ulteriori informazioni sui frammenti di intestazione e sui moduli, vedere [Modulo intestazione](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="4bb3d-129">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4bb3d-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4bb3d-130">Additional resources</span></span>

[<span data-ttu-id="4bb3d-131">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="4bb3d-131">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4bb3d-132">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="4bb3d-132">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="4bb3d-133">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="4bb3d-133">Cookie compliance</span></span>](cookie-compliance.md)
