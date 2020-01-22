---
title: Utilizzare i file di sostituzione CSS
description: Questo argomento descrive perché, quando e come utilizzare i file di sostituzione CSS (Cascading Style Sheets) in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b5a50fc0c9060117cdddc0875446afc2edc12a11
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915441"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="3e219-103">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="3e219-103">Work with CSS override files</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="3e219-104">Questo argomento descrive perché, quando e come utilizzare i file di sostituzione CSS (Cascading Style Sheets) in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e219-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e219-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="3e219-105">Overview</span></span>

<span data-ttu-id="3e219-106">Gli stili permanenti del sito dovrebbero generalmente essere gestiti attraverso un tema del sito.</span><span class="sxs-lookup"><span data-stu-id="3e219-106">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="3e219-107">I temi forniscono i CSS e le impostazioni di stile fondamentali per i moduli su qualsiasi pagina del tuo sito.</span><span class="sxs-lookup"><span data-stu-id="3e219-107">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="3e219-108">I temi vengono creati utilizzando l'SDK online di Dynamics 365 Commerce vengono distribuiti ai siti Web tramite Lifecycle Services (LCS) di Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="3e219-108">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="3e219-109">Le funzionalità di debug dei temi e le configurazioni dell'interfaccia del modulo nell'SDK aiutano gli sviluppatori del sito a creare pacchetti di progettazione del sito personalizzabili e coerenti.</span><span class="sxs-lookup"><span data-stu-id="3e219-109">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="3e219-110">Quando questi pacchetti di progettazione vengono distribuiti in un sito, gli autori del sito possono concentrarsi sulla creazione, la modifica e la pubblicazione di contenuti anziché sullo sviluppo del sito.</span><span class="sxs-lookup"><span data-stu-id="3e219-110">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="3e219-111">Dato il normale ciclo di vita di un tema, la dipendenza dagli sviluppatori per apportare modifiche di stile attraverso la pipeline di distribuzione SDK e LCS può essere proibitiva in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="3e219-111">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="3e219-112">I prototipi o gli aggiornamenti rapidi del sito possono sembrare complicati se l'SDK non è configurato o se non si ha il tempo di attendere una distribuzione LCS.</span><span class="sxs-lookup"><span data-stu-id="3e219-112">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="3e219-113">In questi scenari, i file di sostituzione CSS possono essere di aiuto.</span><span class="sxs-lookup"><span data-stu-id="3e219-113">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="3e219-114">Negli strumenti di creazione di Commerce, gli utenti autenticati possono caricare un file CSS, visualizzalo in anteprima e quindi attivalo per sovrascrivere il tema di un sito.</span><span class="sxs-lookup"><span data-stu-id="3e219-114">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="3e219-115">Non è richiesto il sovraccarico della distribuzione di SDK o LCS.</span><span class="sxs-lookup"><span data-stu-id="3e219-115">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="3e219-116">Le sostituzioni specificate in un file di sostituzione CSS può essere piccolo come una modifica a un singolo stile di testo o ampio come una revisione completa del marchio.</span><span class="sxs-lookup"><span data-stu-id="3e219-116">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="3e219-117">Prima di utilizzare i file di sostituzione CSS, tenere presenti le seguenti limitazioni:</span><span class="sxs-lookup"><span data-stu-id="3e219-117">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="3e219-118">Su un sito può essere attivo un solo file di sostituzione CSS alla volta.</span><span class="sxs-lookup"><span data-stu-id="3e219-118">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="3e219-119">Pertanto, tutte le sostituzioni attive devono essere in un singolo file di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="3e219-119">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="3e219-120">Sebbene sia possibile visualizzare l'anteprima delle sostituzioni negli strumenti di creazione di Commerce, non esistono funzioni di debug dedicate per identificare eventuali bug introdotti dalle sostituzioni.</span><span class="sxs-lookup"><span data-stu-id="3e219-120">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="3e219-121">In altre parole, quando si utilizzano i file di sostituzione CSS, non si dispone dello stesso set di strumenti fornito dall'SDK per la convalida del modulo e della creazione.</span><span class="sxs-lookup"><span data-stu-id="3e219-121">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="3e219-122">Tuttavia, i file di sostituzione CSS forniscono un modo rapido per eseguire il prototipo di un progetto o implementare un aggiornamento rapido prima che venga sviluppato e distribuito un aggiornamento completo del tema.</span><span class="sxs-lookup"><span data-stu-id="3e219-122">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="3e219-123">Creare un file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="3e219-123">Create a CSS override file</span></span>

<span data-ttu-id="3e219-124">Per creare un file di sostituzione CSS, è possibile utilizzare qualsiasi ambiente di sviluppo integrato (IDE), editor di testo o editor di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3e219-124">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="3e219-125">Un approccio tipico consiste nell'utilizzare i debugger Web standard nel browser per identificare selettori di stile, proprietà e valori nel sito esistente.</span><span class="sxs-lookup"><span data-stu-id="3e219-125">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="3e219-126">La maggior parte dei browser consente di modificare i valori e visualizzarli in anteprima nel debugger.</span><span class="sxs-lookup"><span data-stu-id="3e219-126">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="3e219-127">Dopo aver identificato le modifiche che si desidera apportare, è possibile salvarle nel proprio file CSS.</span><span class="sxs-lookup"><span data-stu-id="3e219-127">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="3e219-128">Caricare un file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="3e219-128">Upload a CSS override file</span></span>

<span data-ttu-id="3e219-129">Per caricare un file CSS sul sito in Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3e219-129">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="3e219-130">Negli strumenti di creazione, accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="3e219-130">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="3e219-131">Nel riquadro di navigazione a sinistra, selezionare **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="3e219-131">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e219-132">A seconda della versione degli strumenti di creazione di Commerce che stai utilizzando, potresti dover espandere **Impostazioni** nel riquadro di navigazione prima di poter selezionare **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="3e219-132">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="3e219-133">Nella parte superiore del riquadro di progettazione principale, selezionare la scheda **Sostituzione CSS**, se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="3e219-133">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="3e219-134">In **Sostituzioni CSS disponibili**, Selezionare **Carica file CSS**.</span><span class="sxs-lookup"><span data-stu-id="3e219-134">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="3e219-135">Viene visualizzata una finestra Esplora file.</span><span class="sxs-lookup"><span data-stu-id="3e219-135">A File Explorer window appears.</span></span>
1. <span data-ttu-id="3e219-136">In Esplora file, cercare e selezionare un file CSS, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3e219-136">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="3e219-137">Il file CSS caricato ora appare sotto **Sostituzioni CSS disponibili**.</span><span class="sxs-lookup"><span data-stu-id="3e219-137">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="3e219-138">Anteprima di un file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="3e219-138">Preview a CSS override file</span></span>

<span data-ttu-id="3e219-139">Per visualizzare l'anteprima di un file di sostituzione CSS prima di renderlo attivo sul sito live, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3e219-139">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="3e219-140">Nel riquadro di navigazione a sinistra, selezionare **Progetto** e quindi sulla scheda **Sostituzione CSS**, sotto **Sostituzioni CSS disponibili**, trovare il file CSS che si desidera visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="3e219-140">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="3e219-141">Accanto al nome file CSS, selezionare **Anteprima del sito**.</span><span class="sxs-lookup"><span data-stu-id="3e219-141">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="3e219-142">Nella finestra di dialogo **Seleziona un URL** selezionare l'URL del sito a cui si desidera applicare la sostituzione, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e219-142">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="3e219-143">Se esistono più varianti per l'URL selezionato, selezionare la variante desiderata nella finestra di dialogo **Anteprima delle variazioni** visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3e219-143">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="3e219-144">Viene aperta una nuova scheda o finestra del browser, in cui è possibile convalidare le sostituzioni di stile sul sito.</span><span class="sxs-lookup"><span data-stu-id="3e219-144">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="3e219-145">È quindi possibile condividere l'URL con altri utenti Commerce autenticati per la revisione e il feedback.</span><span class="sxs-lookup"><span data-stu-id="3e219-145">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="3e219-146">Attivare un file di sostituzione CSS sul sito live</span><span class="sxs-lookup"><span data-stu-id="3e219-146">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="3e219-147">Dopo aver visualizzato in anteprima e approvato il file di sostituzione CSS, è possibile attivarlo sul sito live.</span><span class="sxs-lookup"><span data-stu-id="3e219-147">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="3e219-148">Sul sito può essere attivo un solo file di sostituzione CSS alla volta.</span><span class="sxs-lookup"><span data-stu-id="3e219-148">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="3e219-149">Se si attiva un nuovo file di sostituzione, il precedente file di sostituzione viene disattivato.</span><span class="sxs-lookup"><span data-stu-id="3e219-149">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="3e219-150">Pertanto, assicurarsi che tutte le sostituzioni richieste siano presenti in un solo file di sostituzione CSS.</span><span class="sxs-lookup"><span data-stu-id="3e219-150">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="3e219-151">Per attivare un file di sostituzione CSS, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3e219-151">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="3e219-152">Nel riquadro di navigazione a sinistra, selezionare **Progetto** e quindi sulla scheda **Sostituzione CSS**, sotto **Sostituzioni CSS disponibili**, trovare il file CSS che si desidera attivare.</span><span class="sxs-lookup"><span data-stu-id="3e219-152">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="3e219-153">Sotto il nome file CSS, selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="3e219-153">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="3e219-154">Il file di sostituzione diventa immediatamente attivo sul sito live.</span><span class="sxs-lookup"><span data-stu-id="3e219-154">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="3e219-155">Disattivare un file di sostituzione CSS sul sito live</span><span class="sxs-lookup"><span data-stu-id="3e219-155">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="3e219-156">Per disattivare un file di sostituzione CSS sul sito, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3e219-156">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="3e219-157">Nel riquadro di navigazione a sinistra, selezionare **Progetto** e quindi sulla scheda **Sostituzione CSS**, sotto **Sostituzioni CSS disponibili**, trovare il file CSS che si desidera disattivare.</span><span class="sxs-lookup"><span data-stu-id="3e219-157">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="3e219-158">Sotto il nome file CSS, selezionare **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="3e219-158">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="3e219-159">Il file di sostituzione diventa immediatamente inattivo sul sito live.</span><span class="sxs-lookup"><span data-stu-id="3e219-159">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="3e219-160">Per accedere a opzioni aggiuntive per i file di sostituzione CSS, selezionare i puntini di sospensione ( **...**) accanto al nome del file CSS.</span><span class="sxs-lookup"><span data-stu-id="3e219-160">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="3e219-161">Le opzioni **Scarica**, **Rinomina** e **Sostituisci** sono utili per le modifiche rapide a un file di sostituzione CSS esistente.</span><span class="sxs-lookup"><span data-stu-id="3e219-161">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e219-162">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3e219-162">Additional resources</span></span>

[<span data-ttu-id="3e219-163">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="3e219-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="3e219-164">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="3e219-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="3e219-165">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="3e219-165">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="3e219-166">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="3e219-166">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="3e219-167">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="3e219-167">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="3e219-168">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="3e219-168">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="3e219-169">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="3e219-169">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
