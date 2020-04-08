---
title: Aggiungere codice script nelle pagine del sito per supportare la telemetria
description: In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.
author: bicyclingfool
manager: annbe
ms.date: 03/20/2020
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
ms.openlocfilehash: 81c36685c1eccceb2f1854fe7c866186120c08a3
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154088"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="e4c59-103">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="e4c59-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e4c59-104">In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.</span><span class="sxs-lookup"><span data-stu-id="e4c59-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="e4c59-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e4c59-105">Overview</span></span>

<span data-ttu-id="e4c59-106">L'analisi dei dati Web è uno strumento essenziale se si desidera comprendere come i clienti interagiscono con il sito e prendono decisioni che consentono di ottimizzare l'esperienza per la massima conversione.</span><span class="sxs-lookup"><span data-stu-id="e4c59-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="e4c59-107">Molti pacchetti di analisi dei dati Web sono disponibili per consentire il raggiungimento di questi obiettivi, ad esempio Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="e4c59-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="e4c59-108">La maggior parte dei pacchetti di analisi dei dati Web richiede l'aggiunta di codice script sul lato client nell'elemento **\<intestazione\>** del codice HTML per tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="e4c59-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="e4c59-109">Le istruzioni fornite in questo argomento si applicano anche all'altra funzionalità personalizzata sul lato client che Microsoft Dynamics 365 Commerce non offre in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="e4c59-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-page-fragment-for-your-script-code"></a><span data-ttu-id="e4c59-110">Creare un frammento pagina riutilizzabile per il codice script</span><span class="sxs-lookup"><span data-stu-id="e4c59-110">Create a reusable page fragment for your script code</span></span>

<span data-ttu-id="e4c59-111">Un frammento pagina consente di riutilizzare il codice script incorporato o esterno in tutte le pagine del sito, indipendentemente dal modello che utilizzano.</span><span class="sxs-lookup"><span data-stu-id="e4c59-111">A page fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-inline-script-code"></a><span data-ttu-id="e4c59-112">Creare un frammento pagina riutilizzabile per il codice script inline</span><span class="sxs-lookup"><span data-stu-id="e4c59-112">Create a reusable page fragment for your inline script code</span></span>

<span data-ttu-id="e4c59-113">Per creare un frammento di pagina riutilizzabile per il codice di script inline in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e4c59-113">To create a reusable page fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e4c59-114">Andare a **Frammenti pagina** e quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-114">Go to **Page Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="e4c59-115">Nella finestra di dialogo **Nuovo frammento pagina** selezionare **Script inline**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-115">In the **New Page Fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="e4c59-116">Sotto **Nome frammento pagina**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-116">Under **Page Fragment Name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e4c59-117">Sotto il frammento di pagina creato, selezionare il modulo **Script inline predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-117">Under the page fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="e4c59-118">Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client.</span><span class="sxs-lookup"><span data-stu-id="e4c59-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="e4c59-119">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e4c59-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e4c59-120">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e4c59-121">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e4c59-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-external-script-code"></a><span data-ttu-id="e4c59-122">Creare un frammento pagina riutilizzabile per il codice script esterno</span><span class="sxs-lookup"><span data-stu-id="e4c59-122">Create a reusable page fragment for your external script code</span></span>

<span data-ttu-id="e4c59-123">Per creare un frammento di pagina riutilizzabile per il codice di script esterno in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e4c59-123">To create a reusable page fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e4c59-124">Andare a **Frammenti pagina** e quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-124">Go to **Page Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="e4c59-125">Nella finestra di dialogo **Nuovo frammento pagina** selezionare **Script esterno**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-125">In the **New Page Fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="e4c59-126">Sotto **Nome frammento pagina**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-126">Under **Page Fragment Name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e4c59-127">Sotto il frammento di pagina creato, selezionare il modulo **Script esterno predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-127">Under the page fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="e4c59-128">Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno.</span><span class="sxs-lookup"><span data-stu-id="e4c59-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="e4c59-129">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e4c59-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e4c59-130">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e4c59-131">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e4c59-131">Select **Publish**.</span></span>

## <a name="add-a-page-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="e4c59-132">Aggiungere un frammento di pagina che includa il codice dello script in un modello</span><span class="sxs-lookup"><span data-stu-id="e4c59-132">Add a page fragment that includes script code to a template</span></span>

<span data-ttu-id="e4c59-133">Per aggiungere un frammento di pagina che includa codice di script in un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e4c59-133">To add a page fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e4c59-134">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="e4c59-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e4c59-135">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e4c59-136">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**), quindi selezionare **Aggiungi frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Page Fragment**.</span></span>
1. <span data-ttu-id="e4c59-137">Selezionare il frammento creato per il codice script.</span><span class="sxs-lookup"><span data-stu-id="e4c59-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="e4c59-138">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e4c59-139">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e4c59-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="e4c59-140">Aggiungere uno script esterno o uno script inline direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="e4c59-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="e4c59-141">Se si desidera inserire uno script inline o esterno direttamente in un set di pagine controllate da un singolo modello, non è necessario creare prima un frammento di pagina.</span><span class="sxs-lookup"><span data-stu-id="e4c59-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a page fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="e4c59-142">Aggiungere uno script inline direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="e4c59-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="e4c59-143">Per aggiungere uno script inline direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e4c59-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e4c59-144">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="e4c59-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e4c59-145">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e4c59-146">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e4c59-147">Nella finestra di dialogo **Aggiungi modulo** selezionare **Script inline**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="e4c59-148">Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client.</span><span class="sxs-lookup"><span data-stu-id="e4c59-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="e4c59-149">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e4c59-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e4c59-150">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e4c59-151">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e4c59-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="e4c59-152">Aggiungere uno script esterno direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="e4c59-152">Add an external script directly to a template</span></span>

<span data-ttu-id="e4c59-153">Per aggiungere uno script esterno direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e4c59-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e4c59-154">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="e4c59-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e4c59-155">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e4c59-156">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e4c59-157">Nella finestra di dialogo **Aggiungi modulo** selezionare **Script esterno**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="e4c59-158">Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno.</span><span class="sxs-lookup"><span data-stu-id="e4c59-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="e4c59-159">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e4c59-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e4c59-160">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4c59-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e4c59-161">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e4c59-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4c59-162">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e4c59-162">Additional resources</span></span>

[<span data-ttu-id="e4c59-163">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="e4c59-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="e4c59-164">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="e4c59-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e4c59-165">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="e4c59-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e4c59-166">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="e4c59-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e4c59-167">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="e4c59-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e4c59-168">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="e4c59-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="e4c59-169">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="e4c59-169">Add languages to your site</span></span>](add-languages-to-site.md)
