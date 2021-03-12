---
title: Modulo di selezione sito
description: In questo argomento viene descritto il modulo selettore sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: ed00836c435bd391e5edef1f6a99889c80f45211
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985588"
---
# <a name="site-selector-module"></a><span data-ttu-id="b0ff4-103">Modulo di selezione sito</span><span class="sxs-lookup"><span data-stu-id="b0ff4-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b0ff4-104">In questo argomento viene descritto il modulo selettore sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b0ff4-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b0ff4-105">Overview</span></span>

<span data-ttu-id="b0ff4-106">Quando un'azienda ha siti diversi in mercati, regioni e impostazioni locali, gli utenti del sito hanno bisogno di un modo semplice per passare da un sito all'altro e selezionare il loro sito di acquisto preferito.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="b0ff4-107">Per soddisfare questo scenario, il modulo di selezione sito consente agli utenti di spostarsi su più siti.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="b0ff4-108">Il modulo di selezione sito deve essere configurato con l'elenco dei siti (mercati, regioni o impostazioni locali) che gli utenti del sito possono esplorare.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="b0ff4-109">Il modulo di selezione sito è disponibile in Dynamics 365 Commerce versione 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="b0ff4-110">La figura seguente mostra un esempio di un modulo di selezione sito presente nell'intestazione di una pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Esempio di un modulo di selezione sito nell'intestazione di una pagina del sito](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="b0ff4-112">Proprietà del modulo di selezione sito</span><span class="sxs-lookup"><span data-stu-id="b0ff4-112">Site selector module properties</span></span>

| <span data-ttu-id="b0ff4-113">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="b0ff4-113">Property name</span></span> | <span data-ttu-id="b0ff4-114">Valore</span><span class="sxs-lookup"><span data-stu-id="b0ff4-114">Value</span></span>                 | <span data-ttu-id="b0ff4-115">descrizione</span><span class="sxs-lookup"><span data-stu-id="b0ff4-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="b0ff4-116">Intestazione</span><span class="sxs-lookup"><span data-stu-id="b0ff4-116">Heading</span></span>       | <span data-ttu-id="b0ff4-117">Testo</span><span class="sxs-lookup"><span data-stu-id="b0ff4-117">Text</span></span>                  | <span data-ttu-id="b0ff4-118">L'intestazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-118">The heading for the module.</span></span> |
| <span data-ttu-id="b0ff4-119">Opzioni sito</span><span class="sxs-lookup"><span data-stu-id="b0ff4-119">Site options</span></span>  | <span data-ttu-id="b0ff4-120">Nome, immagine, URL</span><span class="sxs-lookup"><span data-stu-id="b0ff4-120">Name, Image, URL</span></span>      | <span data-ttu-id="b0ff4-121">Questa proprietà specifica un nome, un collegamento alla home page del sito e un'immagine facoltativa da mostrare per ogni sito incluso nel modulo.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="b0ff4-122">L'immagine può essere un flag o una rappresentazione di un mercato, una regione o un'impostazione locale.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="b0ff4-123">Aggiungere un modulo di selezione sito a una pagina</span><span class="sxs-lookup"><span data-stu-id="b0ff4-123">Add a site selector module to a page</span></span>

<span data-ttu-id="b0ff4-124">Il modulo di selezione sito può essere aggiunto al [Modulo di intestazione](author-header-module.md) sotto lo slot di selezione sito.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="b0ff4-125">Dopo averlo aggiunto, è possibile definire l'intestazione del modulo e le opzioni del sito.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0ff4-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0ff4-126">Additional resources</span></span>

[<span data-ttu-id="b0ff4-127">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="b0ff4-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b0ff4-128">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="b0ff4-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="b0ff4-129">Modulo percorso di navigazione</span><span class="sxs-lookup"><span data-stu-id="b0ff4-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="b0ff4-130">Modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="b0ff4-130">Navigation menu module</span></span>](nav-menu-module.md)
