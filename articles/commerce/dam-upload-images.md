---
title: Caricare immagini
description: In questo argomento viene descritto come caricare immagini in Creazione di siti Web Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799231"
---
# <a name="upload-images"></a><span data-ttu-id="096f7-103">Caricare immagini</span><span class="sxs-lookup"><span data-stu-id="096f7-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="096f7-104">In questo argomento viene descritto come caricare immagini in Creazione di siti Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="096f7-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="096f7-105">La libreria multimediale Creazione di siti Web Commerce consente di caricare le immagini, singolarmente o in blocco, utilizzando le cartelle.</span><span class="sxs-lookup"><span data-stu-id="096f7-105">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="096f7-106">È sempre necessario caricare la versione dell'immagine con la risoluzione e la qualità più alte, perché il componente di dimensionamento immagine ottimizza automaticamente l'immagine per essere adatta a diversi riquadri di visualizzazione e ai punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="096f7-106">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="096f7-107">Informazioni sull'immagine specificate durante il caricamento</span><span class="sxs-lookup"><span data-stu-id="096f7-107">Image information specified during upload</span></span>

<span data-ttu-id="096f7-108">Quando si carica un'immagine, è possibile specificare le seguenti informazioni.</span><span class="sxs-lookup"><span data-stu-id="096f7-108">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="096f7-109">**Titolo, testo alternativo, Descrizione, parole chiave**: i metadati dell'immagine o delle immagini.</span><span class="sxs-lookup"><span data-stu-id="096f7-109">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="096f7-110">Titolo e testo alternativo sono valori obbligatori.</span><span class="sxs-lookup"><span data-stu-id="096f7-110">Title and alt text are required values.</span></span>
- <span data-ttu-id="096f7-111">**Seleziona categoria**:</span><span class="sxs-lookup"><span data-stu-id="096f7-111">**Select category**:</span></span>
    - <span data-ttu-id="096f7-112">**Nessuna**: utilizzato per un'immagine o immagini di storytelling e-commerce.</span><span class="sxs-lookup"><span data-stu-id="096f7-112">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="096f7-113">**Prodotto, categoria, cliente, dipendente, catalogo**: usati per un'immagine o immagini omnicanale Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="096f7-113">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="096f7-114">**Pubblica risorse dopo il caricamento**: quando questa casella di controllo è selezionata, l'immagine o le immagini vengono pubblicate immediatamente dopo il caricamento.</span><span class="sxs-lookup"><span data-stu-id="096f7-114">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="096f7-115">Le risorse immagine con una categoria assegnata vengono inoltre automaticamente contrassegnate con la categoria come parola chiave per facilitare la ricerca di risorse di una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="096f7-115">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="096f7-116">Convenzioni di denominazione per immagini omnicanale</span><span class="sxs-lookup"><span data-stu-id="096f7-116">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="096f7-117">Se la libreria multimediale è stata configurata come backend dell'immagine omnicanale, è possibile utilizzare le categorie di immagini per indicare a quale categoria appartiene l'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="096f7-117">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="096f7-118">Esiste anche una convenzione di denominazione che deve essere seguita per garantire che le immagini vengano recuperate correttamente da altri canali, come il punto vendita (POS).</span><span class="sxs-lookup"><span data-stu-id="096f7-118">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="096f7-119">La convenzione di denominazione predefinita varia in base alla categoria:</span><span class="sxs-lookup"><span data-stu-id="096f7-119">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="096f7-120">Le immagini del catalogo devono essere denominate "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="096f7-120">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="096f7-121">Le immagini di categoria devono essere denominate "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="096f7-121">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="096f7-122">Le immagini dei clienti devono essere denominate "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="096f7-122">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="096f7-123">Le immagini dei dipendenti devono essere denominate "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="096f7-123">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="096f7-124">Le immagini dei prodotti devono essere denominate "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="096f7-124">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="096f7-125">001 è la sequenza dell'immagine e può essere 001, 002, 003, 004 o 005</span><span class="sxs-lookup"><span data-stu-id="096f7-125">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="096f7-126">Le immagini varianti dei prodotti devono essere denominate "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="096f7-126">Product variant images should be named "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span></span>
    - <span data-ttu-id="096f7-127">Ad esempio: 93039 \^ \^ 2 \^ Black \^_000_001.png</span><span class="sxs-lookup"><span data-stu-id="096f7-127">For example: 93039 \^ \^ 2 \^ Black \^_000_001.png</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="096f7-128">Caricare un'immagine</span><span class="sxs-lookup"><span data-stu-id="096f7-128">Upload an image</span></span>

<span data-ttu-id="096f7-129">Per caricare un'immagine in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="096f7-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="096f7-130">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="096f7-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="096f7-131">Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.</span><span class="sxs-lookup"><span data-stu-id="096f7-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="096f7-132">Nella finestra Esplora file, individuare e selezionare uno o più file immagine da caricare, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="096f7-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="096f7-133">Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.</span><span class="sxs-lookup"><span data-stu-id="096f7-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="096f7-134">Immettere una descrizione e le parole chiave facoltative e selezionare una categoria, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="096f7-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="096f7-135">Se si desidera pubblicare le immagini immediatamente dopo averle caricate, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="096f7-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="096f7-136">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="096f7-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="096f7-137">Caricare una cartella di immagini</span><span class="sxs-lookup"><span data-stu-id="096f7-137">Upload a folder of images</span></span>

<span data-ttu-id="096f7-138">Per caricare in blocco una cartella di immagini in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="096f7-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="096f7-139">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="096f7-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="096f7-140">Sulla barra dei comandi, selezionare **Carica \> Carica cartella**.</span><span class="sxs-lookup"><span data-stu-id="096f7-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="096f7-141">Nella finestra Esplora file, individuare e selezionare una cartella da caricare, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="096f7-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="096f7-142">Nella finestra di dialogo **Carica elementi multimediali**, inserire le parole chiave opzionali e selezionare una categoria, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="096f7-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="096f7-143">Se si desidera pubblicare le immagini nella cartella immediatamente dopo averla caricata, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="096f7-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="096f7-144">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="096f7-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="096f7-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="096f7-145">Additional resources</span></span>

[<span data-ttu-id="096f7-146">Panoramica della gestione risorse digitali</span><span class="sxs-lookup"><span data-stu-id="096f7-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="096f7-147">Caricare video</span><span class="sxs-lookup"><span data-stu-id="096f7-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="096f7-148">Caricare file</span><span class="sxs-lookup"><span data-stu-id="096f7-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="096f7-149">Tagliare immagini</span><span class="sxs-lookup"><span data-stu-id="096f7-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="096f7-150">Personalizzare punti focali immagine</span><span class="sxs-lookup"><span data-stu-id="096f7-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="096f7-151">Caricare e fornire file statici</span><span class="sxs-lookup"><span data-stu-id="096f7-151">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
