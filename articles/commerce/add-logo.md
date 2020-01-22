---
title: Aggiungere un logo
description: In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914624"
---
# <a name="add-a-logo"></a><span data-ttu-id="0ae08-103">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="0ae08-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0ae08-104">In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0ae08-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0ae08-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0ae08-105">Overview</span></span>

<span data-ttu-id="0ae08-106">Quando crei il sito, una delle prime cose che probabilmente farai è aggiungere il logo della tua azienda o del tuo marchio all'intestazione del sito.</span><span class="sxs-lookup"><span data-stu-id="0ae08-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="0ae08-107">Lo starter kit online di Dynamics 365 Commerce fornisce un modulo che semplifica questa attività.</span><span class="sxs-lookup"><span data-stu-id="0ae08-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="0ae08-108">È possibile aggiungere un logo direttamente a un modello, layout o pagina.</span><span class="sxs-lookup"><span data-stu-id="0ae08-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="0ae08-109">In questo modo, puoi facilmente modificare il logo che appare su pagine specifiche o gruppi specifici di pagine.</span><span class="sxs-lookup"><span data-stu-id="0ae08-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="0ae08-110">Tuttavia, questo argomento tratta lo scenario più frequente, in cui aggiungi il logo a un frammento di intestazione che può essere riutilizzato in tutte le pagine del tuo sito.</span><span class="sxs-lookup"><span data-stu-id="0ae08-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ae08-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0ae08-111">Prerequisites</span></span>

<span data-ttu-id="0ae08-112">Prima di poter aggiungere un logo a tutte le pagine del tuo sito, è necessario completare queste attività.</span><span class="sxs-lookup"><span data-stu-id="0ae08-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="0ae08-113">Carica il logo in Gestione risorse digitali, a cui puoi accedere dalla pagina **Risorse**.</span><span class="sxs-lookup"><span data-stu-id="0ae08-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="0ae08-114">Creare un frammento di intestazione</span><span class="sxs-lookup"><span data-stu-id="0ae08-114">Create a header fragment.</span></span> <span data-ttu-id="0ae08-115">Per ulteriori informazioni su come creare e utilizzare i frammenti, vedere [Utilizzare i frammenti ](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="0ae08-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="0ae08-116">Includi il frammento di intestazione nel modello utilizzato dalle pagine del tuo sito per le opzioni di layout e di modulo.</span><span class="sxs-lookup"><span data-stu-id="0ae08-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="0ae08-117">Per ulteriori informazioni sui modelli, vedere [Utilizzare i modelli](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="0ae08-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="0ae08-118">Aggiungere un logo a un frammento di intestazione</span><span class="sxs-lookup"><span data-stu-id="0ae08-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="0ae08-119">Per aggiungere un logo al frammento di intestazione del tuo sito, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="0ae08-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="0ae08-120">Nel riquadro di navigazione a sinistra, selezionare **Frammenti**, quindi selezionare il frammento di intestazione creato.</span><span class="sxs-lookup"><span data-stu-id="0ae08-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="0ae08-121">Selezionare **Estrai**.</span><span class="sxs-lookup"><span data-stu-id="0ae08-121">Select **Check out**.</span></span>
3. <span data-ttu-id="0ae08-122">Espandere lo slot **Intestazione** e lo slot **Logo**.</span><span class="sxs-lookup"><span data-stu-id="0ae08-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="0ae08-123">Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Logo** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="0ae08-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="0ae08-124">Selezionare il modulo del logo.</span><span class="sxs-lookup"><span data-stu-id="0ae08-124">Select the logo module.</span></span>
6. <span data-ttu-id="0ae08-125">Nel riquadro delle proprietà a destra, configurare il modulo del logo in modo che mostri il logo.</span><span class="sxs-lookup"><span data-stu-id="0ae08-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="0ae08-126">Salvare il frammento intestazione, verificarlo e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="0ae08-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="0ae08-127">Dopo aver pubblicato il frammento di intestazione aggiornato, tutte le pagine del sito che utilizzano il modello che contiene il frammento di intestazione mostreranno il logo.</span><span class="sxs-lookup"><span data-stu-id="0ae08-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ae08-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0ae08-128">Additional resources</span></span>

[<span data-ttu-id="0ae08-129">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="0ae08-129">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="0ae08-130">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="0ae08-130">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="0ae08-131">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="0ae08-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="0ae08-132">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="0ae08-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="0ae08-133">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="0ae08-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="0ae08-134">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="0ae08-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="0ae08-135">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="0ae08-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

