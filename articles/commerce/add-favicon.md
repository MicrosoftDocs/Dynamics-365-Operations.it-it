---
title: Aggiungere una favicon
description: In questo argomento viene descritto come aggiungere un favicon al sito.
author: bicyclingfool
manager: annbe
ms.date: 04/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2d95e8b799c3b89418657342868e0ec7e94a86f9
ms.sourcegitcommit: ce79fb570e299a26a644e29da7ceb5a57a1374e6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "3295082"
---
# <a name="add-a-favicon"></a><span data-ttu-id="64270-103">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="64270-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="64270-104">In questo argomento viene descritto come aggiungere un favicon al sito.</span><span class="sxs-lookup"><span data-stu-id="64270-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="64270-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="64270-105">Overview</span></span>

<span data-ttu-id="64270-106">Un favicon è un piccolo file di grafica che viene visualizzato, tra l'altro, in una scheda del browser Web, nella barra degli indirizzi, nella cronologia delle esplorazioni e in segnalibri o preferiti.</span><span class="sxs-lookup"><span data-stu-id="64270-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="64270-107">È consigliabile aggiungere un favicon al sito, poiché rappresenta e rinforza il marchio e consente di differenziare il proprio sito da altri siti visitati dai clienti.</span><span class="sxs-lookup"><span data-stu-id="64270-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="64270-108">Sebbene sia possibile aggiungere più favicon di varie dimensioni e tipi di file al sito, in questo argomento viene descritto coma aggiungere un singolo favicon.</span><span class="sxs-lookup"><span data-stu-id="64270-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="64270-109">Tuttavia, lo stesso processo e la stessa posizione sono utilizzati per aggiungere più favicon.</span><span class="sxs-lookup"><span data-stu-id="64270-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="64270-110">Caricare un favicon nella raccolta di asset del sito</span><span class="sxs-lookup"><span data-stu-id="64270-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="64270-111">Per caricare un favicon nella raccolta di asset del sito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="64270-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="64270-112">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="64270-112">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="64270-113">Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.</span><span class="sxs-lookup"><span data-stu-id="64270-113">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="64270-114">Nella finestra Esplora file andare al file di immagine del favicon da caricare, selezionarlo, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="64270-114">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="64270-115">Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.</span><span class="sxs-lookup"><span data-stu-id="64270-115">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="64270-116">Per pubblicare l'immagine subito dopo il caricamento, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="64270-116">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64270-117">Se non si seleziona la casella di controllo **Pubblica elementi multimediali dopo il caricamento**, è necessario tornare alla pagina **Elementi multimediali** e pubblicare manualmente il favicon in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="64270-117">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="64270-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="64270-118">Select **OK**.</span></span>
1. <span data-ttu-id="64270-119">Nel riquadro delle proprietà a destra, copiare l'URL pubblico del favicon.</span><span class="sxs-lookup"><span data-stu-id="64270-119">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="64270-120">L'URL verrà utilizzato in seguito.</span><span class="sxs-lookup"><span data-stu-id="64270-120">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="64270-121">Creare l'HTML per il favicon</span><span class="sxs-lookup"><span data-stu-id="64270-121">Create the HTML for your favicon</span></span>

<span data-ttu-id="64270-122">Per creare l'HTML per il favicon, usare la stringa HTML seguente.</span><span class="sxs-lookup"><span data-stu-id="64270-122">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="64270-123">Per l'attributo **href**, sostituire **Public\_URL\_for\_your\_favicon** con l'URL pubblico copiato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="64270-123">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-page-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="64270-124">Creare un frammento di pagina contenente un metatag per il favicon</span><span class="sxs-lookup"><span data-stu-id="64270-124">Create a page fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="64270-125">Per creare un frammento di pagina contenente un metatag per il favicon, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="64270-125">To create a page fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="64270-126">Andare a **Frammenti pagina** e selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="64270-126">Go to **Page fragments**, and select **New**.</span></span>
1. <span data-ttu-id="64270-127">Nella finestra di dialogo **Nuovo frammento pagina** selezionare **Metatag** come modulo su cui basare il frammento di pagina.</span><span class="sxs-lookup"><span data-stu-id="64270-127">In the **New Page Fragment** dialog box, select **Metatags** as the module that the page fragment is based on.</span></span>
1. <span data-ttu-id="64270-128">Immettere un nome per il frammento di pagina, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="64270-128">Enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="64270-129">Nell'albero della gerarchia di frammenti, selezionare l'elemento figlio **Metatag predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="64270-129">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="64270-130">Nel riquadro destro, sotto **Metatag**, selezionare **Aggiungi**, quindi immettere la stringa HTML creata in precedenza per il favicon.</span><span class="sxs-lookup"><span data-stu-id="64270-130">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="64270-131">Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il frammento di pagina.</span><span class="sxs-lookup"><span data-stu-id="64270-131">Select **Finish editing**, and then select **Publish** to publish the page fragment.</span></span>

## <a name="add-the-metatag-page-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="64270-132">Aggiungere il frammento di pagina dei metatag alla sezione di intestazione HTML delle pagine</span><span class="sxs-lookup"><span data-stu-id="64270-132">Add the metatag page fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="64270-133">Per aggiungere il frammento di pagina dei metatag alla sezione **head** di intestazione HTML delle pagine, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="64270-133">To add the metatag page fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="64270-134">Andare a **Modelli**, aprire il modello per le pagine a cui aggiungere il favicon, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="64270-134">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="64270-135">Nell'albero della gerarchia dei modelli, selezionare i puntini di sospensione (**...**) a destra del contenitore **Intestazione HTML**, quindi selezionare **Aggiungi frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="64270-135">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add page fragment**.</span></span>
1. <span data-ttu-id="64270-136">Nella finestra di dialogo **Seleziona frammento pagina**, selezionare il frammento di pagina dei metatag creato in precedenza, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="64270-136">In the **Select Page Fragment** dialog box, select the metatag page fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="64270-137">Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il modello.</span><span class="sxs-lookup"><span data-stu-id="64270-137">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="64270-138">Se il tuo sito utilizza più di un modello, è necessario aggiungere il frammento di pagina dei metatag a ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="64270-138">If your site uses more than one template, you must add the metatags page fragment to all of them.</span></span>

<span data-ttu-id="64270-139">Quando si visualizzano in anteprima le pagine basate sul modello a cui è stato aggiunto il frammento di pagina dei metatag, si dovrebbe ora vedere il favicon nella scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="64270-139">When you preview pages that are based on the template that you added the metatags page fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64270-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="64270-140">Additional resources</span></span>

[<span data-ttu-id="64270-141">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="64270-141">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="64270-142">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="64270-142">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="64270-143">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="64270-143">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="64270-144">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="64270-144">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="64270-145">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="64270-145">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="64270-146">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="64270-146">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="64270-147">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="64270-147">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

