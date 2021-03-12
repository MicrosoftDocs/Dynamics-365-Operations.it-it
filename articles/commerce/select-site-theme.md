---
title: Selezionare un tema per il sito
description: In questo argomento viene descritto come impostare o modificare il tema del sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66fcff9fa18d3c98e022ef91d15903fbba8b6b61
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982407"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="9f310-103">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="9f310-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f310-104">In questo argomento viene descritto come impostare o modificare il tema del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f310-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9f310-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9f310-105">Overview</span></span>

<span data-ttu-id="9f310-106">Il layout e lo stile di un sito (ad esempio caratteri, dimensioni e colori) vengono definiti mediante il tema selezionato e applicato al sito.</span><span class="sxs-lookup"><span data-stu-id="9f310-106">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="9f310-107">Un tema viene creato e distribuito da uno sviluppatore nella società.</span><span class="sxs-lookup"><span data-stu-id="9f310-107">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="9f310-108">Per una panoramica dei temi, vedere [Panoramica dello sviluppo di temi](e-commerce-extensibility/theming.md).</span><span class="sxs-lookup"><span data-stu-id="9f310-108">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="9f310-109">Per ulteriori informazioni su come creare e distribuire temi, vedere [Creare un nuovo tema](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="9f310-109">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="9f310-110">Per impostazione predefinita, quando si crea un sito per la prima volta, questo utilizza un tema denominato **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="9f310-110">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="9f310-111">Questo tema predefinito viene fornito con la libreria di moduli di Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f310-111">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="9f310-112">Dopo aver sviluppato temi aggiuntivi per il sito, è possibile configurare il sito di modo che utilizzi uno di questi temi.</span><span class="sxs-lookup"><span data-stu-id="9f310-112">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="9f310-113">Selezionare il tema del sito</span><span class="sxs-lookup"><span data-stu-id="9f310-113">Select the site theme</span></span>

<span data-ttu-id="9f310-114">Per selezionare il tema che viene applicato al sito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="9f310-114">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="9f310-115">Nell'ambiente di creazione di siti, accedere al proprio sito.</span><span class="sxs-lookup"><span data-stu-id="9f310-115">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="9f310-116">Scegliere **Gestione sito** \> **Estendibilità**.</span><span class="sxs-lookup"><span data-stu-id="9f310-116">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="9f310-117">In **Tema**, selezionare un tema nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="9f310-117">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="9f310-118">Per applicare il tema selezionato al sito, selezionare **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="9f310-118">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="9f310-119">Il tema selezionato viene pubblicato nel sito non appena si seleziona **Salva e pubblica** nella pagina **Estendibilità**.</span><span class="sxs-lookup"><span data-stu-id="9f310-119">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="9f310-120">Per visualizzare un'anteprima di un tema nel sito prima di applicarlo, è possibile utilizzare il proprio ambiente di sviluppo o sandbox.</span><span class="sxs-lookup"><span data-stu-id="9f310-120">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f310-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9f310-121">Additional resources</span></span>

[<span data-ttu-id="9f310-122">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="9f310-122">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="9f310-123">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="9f310-123">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="9f310-124">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="9f310-124">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="9f310-125">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="9f310-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="9f310-126">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="9f310-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="9f310-127">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="9f310-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="9f310-128">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="9f310-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="9f310-129">Panoramica dello sviluppo di temi</span><span class="sxs-lookup"><span data-stu-id="9f310-129">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="9f310-130">Creare un nuovo tema</span><span class="sxs-lookup"><span data-stu-id="9f310-130">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)

