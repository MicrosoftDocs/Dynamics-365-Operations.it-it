---
title: Aggiungere un logo
description: In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797601"
---
# <a name="add-a-logo"></a><span data-ttu-id="da5a8-103">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="da5a8-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="da5a8-104">In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="da5a8-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="da5a8-105">Quando crei il sito, una delle prime cose che probabilmente farai è aggiungere il logo della tua azienda o del tuo marchio all'intestazione del sito.</span><span class="sxs-lookup"><span data-stu-id="da5a8-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="da5a8-106">La libreria dei moduli online di Dynamics 365 Commerce fornisce un modulo che semplifica questa attività.</span><span class="sxs-lookup"><span data-stu-id="da5a8-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="da5a8-107">È possibile aggiungere un logo direttamente a un modello, layout o pagina.</span><span class="sxs-lookup"><span data-stu-id="da5a8-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="da5a8-108">In questo modo, puoi facilmente modificare il logo che appare su pagine specifiche o gruppi specifici di pagine.</span><span class="sxs-lookup"><span data-stu-id="da5a8-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="da5a8-109">Tuttavia, questo argomento tratta lo scenario più frequente, in cui aggiungi il logo a un frammento di intestazione che può essere riutilizzato in tutte le pagine del tuo sito.</span><span class="sxs-lookup"><span data-stu-id="da5a8-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="da5a8-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="da5a8-110">Prerequisites</span></span>

<span data-ttu-id="da5a8-111">Prima di poter aggiungere un logo a tutte le pagine del tuo sito, è necessario completare queste attività.</span><span class="sxs-lookup"><span data-stu-id="da5a8-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="da5a8-112">Caricare il logo nella libreria multimediale.</span><span class="sxs-lookup"><span data-stu-id="da5a8-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="da5a8-113">Creare un frammento di intestazione</span><span class="sxs-lookup"><span data-stu-id="da5a8-113">Create a header fragment.</span></span> <span data-ttu-id="da5a8-114">Per ulteriori informazioni su come creare e utilizzare i frammenti, vedere [Utilizzare i frammenti ](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="da5a8-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="da5a8-115">Includi il frammento di intestazione nel modello utilizzato dalle pagine del tuo sito per le opzioni di layout e di modulo.</span><span class="sxs-lookup"><span data-stu-id="da5a8-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="da5a8-116">Per ulteriori informazioni sui modelli, vedere [Utilizzare i modelli](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="da5a8-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="da5a8-117">Aggiungere un logo a un frammento di intestazione</span><span class="sxs-lookup"><span data-stu-id="da5a8-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="da5a8-118">Per aggiungere un logo al frammento di intestazione del tuo sito, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="da5a8-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="da5a8-119">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="da5a8-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="da5a8-120">Selezionare il frammento intestazione creato e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="da5a8-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="da5a8-121">Espandere il modulo di intestazione.</span><span class="sxs-lookup"><span data-stu-id="da5a8-121">Expand the header module.</span></span>
1. <span data-ttu-id="da5a8-122">Nel riquadro delle proprietà per il modulo di intestazione, fornire un'immagine e un collegamento per il logo.</span><span class="sxs-lookup"><span data-stu-id="da5a8-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="da5a8-123">Salvare il frammento intestazione, finalizzare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="da5a8-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="da5a8-124">Dopo aver pubblicato il frammento di intestazione aggiornato, tutte le pagine del sito che utilizzano il modello che contiene il frammento di intestazione mostreranno il logo.</span><span class="sxs-lookup"><span data-stu-id="da5a8-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da5a8-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="da5a8-125">Additional resources</span></span>

[<span data-ttu-id="da5a8-126">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="da5a8-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="da5a8-127">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="da5a8-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="da5a8-128">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="da5a8-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="da5a8-129">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="da5a8-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="da5a8-130">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="da5a8-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="da5a8-131">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="da5a8-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="da5a8-132">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="da5a8-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
