---
title: Aggiungere codice script nelle pagine del sito per supportare la telemetria
description: In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
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
ms.openlocfilehash: dfebc6616186a3a8859b00e90c178129feaa324b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980159"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="25ca9-103">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="25ca9-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="25ca9-104">In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.</span><span class="sxs-lookup"><span data-stu-id="25ca9-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="25ca9-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="25ca9-105">Overview</span></span>

<span data-ttu-id="25ca9-106">L'analisi dei dati Web è uno strumento essenziale se si desidera comprendere come i clienti interagiscono con il sito e prendono decisioni che consentono di ottimizzare l'esperienza per la massima conversione.</span><span class="sxs-lookup"><span data-stu-id="25ca9-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="25ca9-107">Molti pacchetti di analisi dei dati Web sono disponibili per consentire il raggiungimento di questi obiettivi, ad esempio Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="25ca9-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="25ca9-108">La maggior parte dei pacchetti di analisi dei dati Web richiede l'aggiunta di codice script sul lato client nell'elemento **\<head\>** del codice HTML per tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="25ca9-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="25ca9-109">Le istruzioni fornite in questo argomento si applicano anche all'altra funzionalità personalizzata sul lato client che Microsoft Dynamics 365 Commerce non offre in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="25ca9-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="25ca9-110">Creare un frammento riutilizzabile per il codice script</span><span class="sxs-lookup"><span data-stu-id="25ca9-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="25ca9-111">Un frammento consente di riutilizzare il codice script incorporato o esterno in tutte le pagine del sito, indipendentemente dal modello che utilizzano.</span><span class="sxs-lookup"><span data-stu-id="25ca9-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="25ca9-112">Creare un frammento riutilizzabile per il codice script inline</span><span class="sxs-lookup"><span data-stu-id="25ca9-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="25ca9-113">Per creare un frammento riutilizzabile per il codice di script inline in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="25ca9-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="25ca9-114">Andare a **Frammenti** quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="25ca9-115">Nella finestra di dialogo **Nuovo frammento** selezionare **Script inline**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="25ca9-116">Sotto **Nome frammento**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="25ca9-117">Sotto il frammento creato, selezionare il modulo **Script inline predefinito**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="25ca9-118">Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client.</span><span class="sxs-lookup"><span data-stu-id="25ca9-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="25ca9-119">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25ca9-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="25ca9-120">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="25ca9-121">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="25ca9-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="25ca9-122">Creare un frammento riutilizzabile per il codice script esterno</span><span class="sxs-lookup"><span data-stu-id="25ca9-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="25ca9-123">Per creare un frammento riutilizzabile per il codice di script esterno in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="25ca9-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="25ca9-124">Andare a **Frammenti** quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="25ca9-125">Nella finestra di dialogo **Nuovo frammento** selezionare **Script esterno**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="25ca9-126">Sotto **Nome frammento**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="25ca9-127">Sotto il frammento creato, selezionare il modulo **Script esterno predefinito**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="25ca9-128">Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno.</span><span class="sxs-lookup"><span data-stu-id="25ca9-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="25ca9-129">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25ca9-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="25ca9-130">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="25ca9-131">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="25ca9-131">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="25ca9-132">Se i criteri di sicurezza dei contenuti (CSP) sono abilitati per il tuo sito, assicurati che tutti gli URL esterni vengano aggiunti alla direttiva CSP **script-src** in Creazione di siti Web di Commerce.</span><span class="sxs-lookup"><span data-stu-id="25ca9-132">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="25ca9-133">Per altre informazioni, vedere [Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="25ca9-133">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="25ca9-134">Aggiungere un frammento che includa il codice dello script in un modello</span><span class="sxs-lookup"><span data-stu-id="25ca9-134">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="25ca9-135">Per aggiungere un frammento che includa codice di script in un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="25ca9-135">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="25ca9-136">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="25ca9-136">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="25ca9-137">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-137">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="25ca9-138">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-138">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="25ca9-139">Selezionare il frammento creato per il codice script.</span><span class="sxs-lookup"><span data-stu-id="25ca9-139">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="25ca9-140">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-140">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="25ca9-141">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="25ca9-141">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="25ca9-142">Aggiungere uno script esterno o uno script inline direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="25ca9-142">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="25ca9-143">Se si desidera inserire uno script inline o esterno direttamente in un set di pagine controllate da un singolo modello, non è necessario creare prima un frammento.</span><span class="sxs-lookup"><span data-stu-id="25ca9-143">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="25ca9-144">Aggiungere uno script inline direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="25ca9-144">Add an inline script directly to a template</span></span>

<span data-ttu-id="25ca9-145">Per aggiungere uno script inline direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="25ca9-145">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="25ca9-146">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="25ca9-146">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="25ca9-147">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-147">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="25ca9-148">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-148">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="25ca9-149">Nella finestra di dialogo **Aggiungi modulo** selezionare **Script inline**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-149">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="25ca9-150">Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client.</span><span class="sxs-lookup"><span data-stu-id="25ca9-150">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="25ca9-151">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25ca9-151">Then configure other options as you require.</span></span>
1. <span data-ttu-id="25ca9-152">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-152">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="25ca9-153">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="25ca9-153">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="25ca9-154">Aggiungere uno script esterno direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="25ca9-154">Add an external script directly to a template</span></span>

<span data-ttu-id="25ca9-155">Per aggiungere uno script esterno direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="25ca9-155">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="25ca9-156">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="25ca9-156">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="25ca9-157">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-157">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="25ca9-158">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-158">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="25ca9-159">Nella finestra di dialogo **Aggiungi modulo** selezionare **Script esterno**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-159">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="25ca9-160">Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno.</span><span class="sxs-lookup"><span data-stu-id="25ca9-160">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="25ca9-161">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25ca9-161">Then configure other options as you require.</span></span>
1. <span data-ttu-id="25ca9-162">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="25ca9-162">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="25ca9-163">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="25ca9-163">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25ca9-164">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="25ca9-164">Additional resources</span></span>

[<span data-ttu-id="25ca9-165">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="25ca9-165">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="25ca9-166">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="25ca9-166">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="25ca9-167">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="25ca9-167">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="25ca9-168">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="25ca9-168">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="25ca9-169">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="25ca9-169">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="25ca9-170">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="25ca9-170">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="25ca9-171">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="25ca9-171">Add languages to your site</span></span>](add-languages-to-site.md)
