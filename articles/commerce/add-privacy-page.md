---
title: Aggiungere una pagina dell'Informativa sulla privacy
description: In questo argomento viene descritto come aggiungere al sito una pagina dell'Informativa sulla privacy in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59a2d9712a73c607cf5521f8e79e8e2558854fc4
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "3274213"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="0c0ed-103">Aggiungere una pagina dell'Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="0c0ed-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0c0ed-104">In questo argomento viene descritto come aggiungere al sito una pagina dell'Informativa sulla privacy in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0c0ed-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0c0ed-105">Overview</span></span>

<span data-ttu-id="0c0ed-106">La conformità alla privacy include misure organizzative che informano gli utenti del sito su come i loro dati vengono raccolti e gestiti.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="0c0ed-107">Gli utenti possono quindi decidere come desiderano vengano gestiti i propri dati personali e intraprendere le azioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="0c0ed-108">Rivedi l'Informativa sulla privacy di Microsoft in Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0c0ed-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="0c0ed-109">Per rivedere l'Informativa sulla privacy di Microsoft mentre è stato eseguito l'accesso agli strumenti di creazione di Dynamics 365 Commerce, selezionare il pulsante della **Guida** ( **?**) nell'angolo in alto a destra, quindi selezionare **Privacy e cookie**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="0c0ed-110">Si apre una nuova scheda con un collegamento all'[Informativa sulla privacy di Microsoft ](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="0c0ed-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="0c0ed-111">Creare una pagina di informativa sulla privacy per il tuo sito</span><span class="sxs-lookup"><span data-stu-id="0c0ed-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="0c0ed-112">In Dynamics 365 Commerce, esistono diversi modi per fornire agli utenti del sito l'accesso all'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="0c0ed-113">Questa sezione mostra come creare una pagina dell'informativa sulla privacy e quindi fare riferimento alla pagina utilizzando un frammento di piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="0c0ed-114">Le linee guida che seguono sono un esempio che mostra come creare una pagina di informativa sulla privacy generica per un sito commerciale.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="0c0ed-115">L'utente è responsabile della progettazione e dell'implementazione di una soluzione di pagina di informativa sulla privacy che soddisfa al meglio i requisiti legali dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="0c0ed-116">Per iniziare, negli strumenti di creazione, vai al sito per cui desideri creare una pagina di informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="0c0ed-117">Creare un modello</span><span class="sxs-lookup"><span data-stu-id="0c0ed-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="0c0ed-118">Se è già stato creato un modello che può essere utilizzato per la pagina dell'informativa sulla privacy, passare alla sezione [Creare una pagina di informativa sulla privacy ](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="0c0ed-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="0c0ed-119">Per creare un nuovo modello, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="0c0ed-120">Andare a **Modelli**, quindi selezionare **Nuovo** per creare un modello di pagina.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-120">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="0c0ed-121">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello banner promozionale**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-121">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="0c0ed-122">Nel modello, aggiungere eventuali moduli necessari per gli slot di pagina richiesti.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="0c0ed-123">Per le linee guida, passare con il mouse sopra i punti esclamativi rossi.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-123">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="0c0ed-124">Ad esempio, lo slot **Intestazione HTML** potrebbe richiedere un modulo **Script esterno predefinito**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-124">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="0c0ed-125">Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="0c0ed-126">Nel modulo **Pagina predefinita** nello slot **Principale**, aggiungere un modulo **Blocco ricco di contenuti**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="0c0ed-127">Nel modulo **Blocco ricco di contenuti**, aggiungi un modulo **Elemento blocco ricco di contenuti**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="0c0ed-128">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-128">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="0c0ed-129">Creare una pagina dell'Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="0c0ed-129">Build a privacy policy page</span></span>

<span data-ttu-id="0c0ed-130">Per creare una pagina di informativa sulla privacy, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="0c0ed-131">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una pagina.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-131">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="0c0ed-132">Nella finestra di dialogo **Scegli un modello**, selezionare il modello per la pagina dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-132">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="0c0ed-133">Immettere un nome e un URL per la pagina e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-133">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="0c0ed-134">Nello slot **Principale**della pagina, aggiungere un modulo **Blocco ricco di contenuti**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="0c0ed-135">Nel modulo **Blocco ricco di contenuti**, aggiungi un modulo **Elemento blocco ricco di contenuti**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="0c0ed-136">Nel riquadro delle proprietà del modulo **Blocco ricco di contenuti**, selezionare **Aggiungi origine dati**, quindi selezionare **Contenuto RTF**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="0c0ed-137">Nell'editor di testo RTF, immettere il contenuto per la pagina dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="0c0ed-138">Espandere l'editor di testo RTF nella modalità a schermo intero in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="0c0ed-139">Dopo aver inserito i contenuti, selezionare **Anteprima**per visualizzare l'anteprima della pagina nel browser Web.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="0c0ed-140">Completa eventuali aggiunte restanti alla pagina e alle proprietà del modulo.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="0c0ed-141">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-141">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="0c0ed-142">Per pubblicare l'URL per la pagina dell'informativa sulla privacy, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="0c0ed-143">Vai a **URL**e seleziona l'URL per la pagina dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="0c0ed-144">Selezionare **Pubblica** per pubblicare l'URL selezionato.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-144">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="0c0ed-145">Creare un collegamento alla pagina dell'informativa sulla privacy in un piè di pagina</span><span class="sxs-lookup"><span data-stu-id="0c0ed-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="0c0ed-146">È possibile aggiungere un collegamento alla pagina dell'informativa sulla privacy a un frammento.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="0c0ed-147">In questo modo, è possibile condividere il collegamento e aggiornarlo su più pagine del sito facendo riferimento al frammento.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="0c0ed-148">Questo esempio mostra come aggiungere un collegamento alla pagina dell'informativa sulla privacy a un frammento di piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="0c0ed-149">Per aggiungere un collegamento a un frammento di piè di pagina, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="0c0ed-150">Andare a **Frammenti pagina** e quindi selezionare **Nuovo** per creare un nuovo frammento di pagina.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-150">Go to **Page Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="0c0ed-151">Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo **Piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-151">In the **New Page Fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="0c0ed-152">Sotto **Nome frammento pagina**, inserire un nome per il frammento, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-152">Under **Page Fragment Name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="0c0ed-153">Nello slot **Categoria piè di pagina**, aggiungere un modulo **Elemento piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-153">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="0c0ed-154">Nel riquadro delle proprietà a destra, selezionare **Testo collegamento**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-154">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="0c0ed-155">Nella finestra di dialogo **Testo collegamento**, immettere il testo del collegamento e la destinazione del collegamento della pagina dell'informativa sulla privacy, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-155">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="0c0ed-156">Per ottenere l'URL della pagina dell'informativa sulla privacy, vai a **Pagine**, quindi alla pagina dell'informativa sulla privacy e copia l'URL dal riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-156">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="0c0ed-157">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-157">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="0c0ed-158">Visualizzare l'anteprima del frammento e testare il link alla pagina dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-158">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="0c0ed-159">Ora è possibile fare riferimento al frammento nel modello per altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-159">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="0c0ed-160">Quando si fa riferimento a questo frammento nel modulo **Piè di pagina** di un modello, il riferimento al collegamento apparirà su tutte le pagine create utilizzando quel modello.</span><span class="sxs-lookup"><span data-stu-id="0c0ed-160">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c0ed-161">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0c0ed-161">Additional resources</span></span>

[<span data-ttu-id="0c0ed-162">Panoramica sulla conformità</span><span class="sxs-lookup"><span data-stu-id="0c0ed-162">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="0c0ed-163">Funzionalità e capacità di accessibilità</span><span class="sxs-lookup"><span data-stu-id="0c0ed-163">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="0c0ed-164">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="0c0ed-164">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="0c0ed-165">Sostituire gli ID utente associati alle modifiche al contenuto monitorato</span><span class="sxs-lookup"><span data-stu-id="0c0ed-165">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
