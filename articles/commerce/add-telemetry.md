---
title: Aggiungere codice script nelle pagine del sito per supportare la telemetria
description: In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697338"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="d8958-103">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="d8958-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d8958-104">In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.</span><span class="sxs-lookup"><span data-stu-id="d8958-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="d8958-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d8958-105">Overview</span></span>

<span data-ttu-id="d8958-106">L'analisi dei dati Web è uno strumento essenziale se si desidera comprendere come i clienti interagiscono con il sito e prendono decisioni che consentono di ottimizzare l'esperienza per la massima conversione.</span><span class="sxs-lookup"><span data-stu-id="d8958-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="d8958-107">Molti pacchetti di analisi dei dati Web sono disponibili per consentire il raggiungimento di questi obiettivi, ad esempio Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="d8958-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="d8958-108">La maggior parte dei pacchetti di analisi dei dati Web richiede l'aggiunta di codice script sul lato client nell'elemento **\<intestazione\>** del codice HTML per tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="d8958-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="d8958-109">Le istruzioni fornite in questo argomento si applicano anche all'altra funzionalità personalizzata sul lato client che Microsoft Dynamics 365 Commerce non offre in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="d8958-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="d8958-110">Creare un frammento riutilizzabile per il codice script</span><span class="sxs-lookup"><span data-stu-id="d8958-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="d8958-111">Dopo aver creato un frammento per il codice script, può essere riutilizzato in tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="d8958-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="d8958-112">Andare a **Frammenti \> Nuovo frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="d8958-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="d8958-113">Selezionare **Script esterno**, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8958-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="d8958-114">Nella gerarchia di frammenti, selezionare l'elemento figlio del modulo **Injector script** del frammento appena creato.</span><span class="sxs-lookup"><span data-stu-id="d8958-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="d8958-115">Nel riquadro delle proprietà a destra, aggiungere lo script sul lato client e impostare altre opzioni di configurazione come necessario.</span><span class="sxs-lookup"><span data-stu-id="d8958-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="d8958-116">Aggiungere il frammento ai modelli</span><span class="sxs-lookup"><span data-stu-id="d8958-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="d8958-117">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="d8958-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="d8958-118">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="d8958-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="d8958-119">Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Intestazione HTML** e quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="d8958-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="d8958-120">Selezionare il frammento creato per il codice script.</span><span class="sxs-lookup"><span data-stu-id="d8958-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="d8958-121">Salvare il modello e verificarlo.</span><span class="sxs-lookup"><span data-stu-id="d8958-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="d8958-122">Al termine, è necessario pubblicare il frammento e il modello generale.</span><span class="sxs-lookup"><span data-stu-id="d8958-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="d8958-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d8958-123">Additional resources</span></span>

[<span data-ttu-id="d8958-124">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="d8958-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="d8958-125">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="d8958-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="d8958-126">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="d8958-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="d8958-127">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="d8958-127">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="d8958-128">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="d8958-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="d8958-129">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="d8958-129">Add languages to your site</span></span>](add-languages-to-site.md)
