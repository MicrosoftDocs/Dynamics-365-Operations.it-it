---
title: Aggiungere un logo
description: In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 143c1ab33547119ceab0a4fba165669bc8b22bf4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207581"
---
# <a name="add-a-logo"></a><span data-ttu-id="28668-103">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="28668-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="28668-104">In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="28668-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="28668-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="28668-105">Overview</span></span>

<span data-ttu-id="28668-106">Quando crei il sito, una delle prime cose che probabilmente farai è aggiungere il logo della tua azienda o del tuo marchio all'intestazione del sito.</span><span class="sxs-lookup"><span data-stu-id="28668-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="28668-107">La libreria dei moduli online di Dynamics 365 Commerce fornisce un modulo che semplifica questa attività.</span><span class="sxs-lookup"><span data-stu-id="28668-107">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="28668-108">È possibile aggiungere un logo direttamente a un modello, layout o pagina.</span><span class="sxs-lookup"><span data-stu-id="28668-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="28668-109">In questo modo, puoi facilmente modificare il logo che appare su pagine specifiche o gruppi specifici di pagine.</span><span class="sxs-lookup"><span data-stu-id="28668-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="28668-110">Tuttavia, questo argomento tratta lo scenario più frequente, in cui aggiungi il logo a un frammento di intestazione che può essere riutilizzato in tutte le pagine del tuo sito.</span><span class="sxs-lookup"><span data-stu-id="28668-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28668-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="28668-111">Prerequisites</span></span>

<span data-ttu-id="28668-112">Prima di poter aggiungere un logo a tutte le pagine del tuo sito, è necessario completare queste attività.</span><span class="sxs-lookup"><span data-stu-id="28668-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="28668-113">Caricare il logo nella libreria multimediale.</span><span class="sxs-lookup"><span data-stu-id="28668-113">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="28668-114">Creare un frammento di intestazione</span><span class="sxs-lookup"><span data-stu-id="28668-114">Create a header fragment.</span></span> <span data-ttu-id="28668-115">Per ulteriori informazioni su come creare e utilizzare i frammenti, vedere [Utilizzare i frammenti ](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="28668-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="28668-116">Includi il frammento di intestazione nel modello utilizzato dalle pagine del tuo sito per le opzioni di layout e di modulo.</span><span class="sxs-lookup"><span data-stu-id="28668-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="28668-117">Per ulteriori informazioni sui modelli, vedere [Utilizzare i modelli](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="28668-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="28668-118">Aggiungere un logo a un frammento di intestazione</span><span class="sxs-lookup"><span data-stu-id="28668-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="28668-119">Per aggiungere un logo al frammento di intestazione del tuo sito, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="28668-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="28668-120">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="28668-120">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="28668-121">Selezionare il frammento intestazione creato e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="28668-121">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="28668-122">Espandere il modulo di intestazione.</span><span class="sxs-lookup"><span data-stu-id="28668-122">Expand the header module.</span></span>
1. <span data-ttu-id="28668-123">Nel riquadro delle proprietà per il modulo di intestazione, fornire un'immagine e un collegamento per il logo.</span><span class="sxs-lookup"><span data-stu-id="28668-123">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="28668-124">Salvare il frammento intestazione, finalizzare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="28668-124">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="28668-125">Dopo aver pubblicato il frammento di intestazione aggiornato, tutte le pagine del sito che utilizzano il modello che contiene il frammento di intestazione mostreranno il logo.</span><span class="sxs-lookup"><span data-stu-id="28668-125">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28668-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="28668-126">Additional resources</span></span>

[<span data-ttu-id="28668-127">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="28668-127">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="28668-128">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="28668-128">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="28668-129">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="28668-129">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="28668-130">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="28668-130">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="28668-131">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="28668-131">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="28668-132">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="28668-132">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="28668-133">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="28668-133">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]