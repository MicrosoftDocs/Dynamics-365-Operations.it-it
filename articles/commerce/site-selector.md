---
title: Modulo di selezione sito
description: In questo argomento viene descritto il modulo di selezione sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 6e8eefe7afe385ca77eca6027638ff938e1356e3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791777"
---
# <a name="site-selector-module"></a><span data-ttu-id="d8bb6-103">Modulo di selezione sito</span><span class="sxs-lookup"><span data-stu-id="d8bb6-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d8bb6-104">In questo argomento viene descritto il modulo di selezione sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d8bb6-105">Quando un'azienda ha siti diversi in mercati, regioni e impostazioni locali, gli utenti del sito hanno bisogno di un modo semplice per passare da un sito all'altro e selezionare il loro sito di acquisto preferito.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-105">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="d8bb6-106">Per soddisfare questo scenario, il modulo di selezione sito consente agli utenti di spostarsi su più siti.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-106">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="d8bb6-107">Il modulo di selezione sito deve essere configurato con l'elenco dei siti (mercati, regioni o impostazioni locali) che gli utenti del sito possono esplorare.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-107">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="d8bb6-108">Il modulo di selezione sito è disponibile in Dynamics 365 Commerce versione 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-108">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="d8bb6-109">La figura seguente mostra un esempio di un modulo di selezione sito presente nell'intestazione di una pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-109">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Esempio di un modulo di selezione sito nell'intestazione di una pagina del sito](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="d8bb6-111">Proprietà del modulo di selezione sito</span><span class="sxs-lookup"><span data-stu-id="d8bb6-111">Site selector module properties</span></span>

| <span data-ttu-id="d8bb6-112">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="d8bb6-112">Property name</span></span> | <span data-ttu-id="d8bb6-113">Valore</span><span class="sxs-lookup"><span data-stu-id="d8bb6-113">Value</span></span>                 | <span data-ttu-id="d8bb6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8bb6-114">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="d8bb6-115">Intestazione</span><span class="sxs-lookup"><span data-stu-id="d8bb6-115">Heading</span></span>       | <span data-ttu-id="d8bb6-116">Testo</span><span class="sxs-lookup"><span data-stu-id="d8bb6-116">Text</span></span>                  | <span data-ttu-id="d8bb6-117">L'intestazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-117">The heading for the module.</span></span> |
| <span data-ttu-id="d8bb6-118">Opzioni sito</span><span class="sxs-lookup"><span data-stu-id="d8bb6-118">Site options</span></span>  | <span data-ttu-id="d8bb6-119">Nome, immagine, URL</span><span class="sxs-lookup"><span data-stu-id="d8bb6-119">Name, Image, URL</span></span>      | <span data-ttu-id="d8bb6-120">Questa proprietà specifica un nome, un collegamento alla home page del sito e un'immagine facoltativa da mostrare per ogni sito incluso nel modulo.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-120">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="d8bb6-121">L'immagine può essere un flag o una rappresentazione di un mercato, una regione o un'impostazione locale.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-121">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="d8bb6-122">Aggiungere un modulo di selezione sito a una pagina</span><span class="sxs-lookup"><span data-stu-id="d8bb6-122">Add a site selector module to a page</span></span>

<span data-ttu-id="d8bb6-123">Il modulo di selezione sito può essere aggiunto al [Modulo di intestazione](author-header-module.md) sotto lo slot di selezione sito.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-123">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="d8bb6-124">Dopo averlo aggiunto, è possibile definire l'intestazione del modulo e le opzioni del sito.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-124">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d8bb6-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d8bb6-125">Additional resources</span></span>

[<span data-ttu-id="d8bb6-126">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="d8bb6-126">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d8bb6-127">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="d8bb6-127">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="d8bb6-128">Modulo percorso di navigazione</span><span class="sxs-lookup"><span data-stu-id="d8bb6-128">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="d8bb6-129">Modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="d8bb6-129">Navigation menu module</span></span>](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]