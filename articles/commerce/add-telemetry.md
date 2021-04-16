---
title: Aggiungere codice script nelle pagine del sito per supportare la telemetria
description: In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797433"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="e71c7-103">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="e71c7-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e71c7-104">In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.</span><span class="sxs-lookup"><span data-stu-id="e71c7-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="e71c7-105">L'analisi dei dati Web è uno strumento essenziale se si desidera comprendere come i clienti interagiscono con il sito e prendono decisioni che consentono di ottimizzare l'esperienza per la massima conversione.</span><span class="sxs-lookup"><span data-stu-id="e71c7-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="e71c7-106">Molti pacchetti di analisi dei dati Web sono disponibili per consentire il raggiungimento di questi obiettivi, ad esempio Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="e71c7-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="e71c7-107">La maggior parte dei pacchetti di analisi dei dati Web richiede l'aggiunta di codice script sul lato client nell'elemento **\<head\>** del codice HTML per tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="e71c7-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="e71c7-108">Le istruzioni fornite in questo argomento si applicano anche all'altra funzionalità personalizzata sul lato client che Microsoft Dynamics 365 Commerce non offre in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="e71c7-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="e71c7-109">Creare un frammento riutilizzabile per il codice script</span><span class="sxs-lookup"><span data-stu-id="e71c7-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="e71c7-110">Un frammento consente di riutilizzare il codice script incorporato o esterno in tutte le pagine del sito, indipendentemente dal modello che utilizzano.</span><span class="sxs-lookup"><span data-stu-id="e71c7-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="e71c7-111">Creare un frammento riutilizzabile per il codice script inline</span><span class="sxs-lookup"><span data-stu-id="e71c7-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="e71c7-112">Per creare un frammento riutilizzabile per il codice di script inline in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e71c7-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e71c7-113">Andare a **Frammenti** quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="e71c7-114">Nella finestra di dialogo **Nuovo frammento** selezionare **Script inline**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="e71c7-115">Sotto **Nome frammento**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e71c7-116">Sotto il frammento creato, selezionare il modulo **Script inline predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="e71c7-117">Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client.</span><span class="sxs-lookup"><span data-stu-id="e71c7-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="e71c7-118">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e71c7-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e71c7-119">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e71c7-120">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e71c7-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="e71c7-121">Creare un frammento riutilizzabile per il codice script esterno</span><span class="sxs-lookup"><span data-stu-id="e71c7-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="e71c7-122">Per creare un frammento riutilizzabile per il codice di script esterno in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e71c7-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e71c7-123">Andare a **Frammenti** quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="e71c7-124">Nella finestra di dialogo **Nuovo frammento** selezionare **Script esterno**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="e71c7-125">Sotto **Nome frammento**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e71c7-126">Sotto il frammento creato, selezionare il modulo **Script esterno predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="e71c7-127">Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno.</span><span class="sxs-lookup"><span data-stu-id="e71c7-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="e71c7-128">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e71c7-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e71c7-129">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e71c7-130">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e71c7-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e71c7-131">Se i criteri di sicurezza dei contenuti (CSP) sono abilitati per il tuo sito, assicurati che tutti gli URL esterni vengano aggiunti alla direttiva CSP **script-src** in Creazione di siti Web di Commerce.</span><span class="sxs-lookup"><span data-stu-id="e71c7-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="e71c7-132">Per altre informazioni, vedere [Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="e71c7-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="e71c7-133">Aggiungere un frammento che includa il codice dello script in un modello</span><span class="sxs-lookup"><span data-stu-id="e71c7-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="e71c7-134">Per aggiungere un frammento che includa codice di script in un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e71c7-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e71c7-135">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="e71c7-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e71c7-136">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e71c7-137">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="e71c7-138">Selezionare il frammento creato per il codice script.</span><span class="sxs-lookup"><span data-stu-id="e71c7-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="e71c7-139">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e71c7-140">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e71c7-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="e71c7-141">Aggiungere uno script esterno o uno script inline direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="e71c7-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="e71c7-142">Se si desidera inserire uno script inline o esterno direttamente in un set di pagine controllate da un singolo modello, non è necessario creare prima un frammento.</span><span class="sxs-lookup"><span data-stu-id="e71c7-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="e71c7-143">Aggiungere uno script inline direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="e71c7-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="e71c7-144">Per aggiungere uno script inline direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e71c7-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e71c7-145">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="e71c7-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e71c7-146">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e71c7-147">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e71c7-148">Nella finestra di dialogo **Aggiungi modulo** selezionare **Script inline**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="e71c7-149">Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client.</span><span class="sxs-lookup"><span data-stu-id="e71c7-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="e71c7-150">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e71c7-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e71c7-151">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e71c7-152">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e71c7-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="e71c7-153">Aggiungere uno script esterno direttamente a un modello</span><span class="sxs-lookup"><span data-stu-id="e71c7-153">Add an external script directly to a template</span></span>

<span data-ttu-id="e71c7-154">Per aggiungere uno script esterno direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e71c7-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e71c7-155">Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.</span><span class="sxs-lookup"><span data-stu-id="e71c7-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e71c7-156">Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e71c7-157">Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e71c7-158">Nella finestra di dialogo **Aggiungi modulo** selezionare **Script esterno**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="e71c7-159">Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno.</span><span class="sxs-lookup"><span data-stu-id="e71c7-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="e71c7-160">Quindi configurare altre opzioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e71c7-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e71c7-161">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="e71c7-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e71c7-162">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="e71c7-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e71c7-163">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e71c7-163">Additional resources</span></span>

[<span data-ttu-id="e71c7-164">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="e71c7-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="e71c7-165">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="e71c7-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e71c7-166">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="e71c7-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e71c7-167">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="e71c7-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e71c7-168">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="e71c7-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e71c7-169">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="e71c7-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="e71c7-170">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="e71c7-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
