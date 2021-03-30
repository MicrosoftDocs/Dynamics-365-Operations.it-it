---
title: Caricare immagini
description: In questo argomento viene descritto come caricare immagini in Creazione di siti Web Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 51571ce221714598b2e2d39c76cb69dcb57cc52b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213796"
---
# <a name="upload-images"></a><span data-ttu-id="77787-103">Caricare immagini</span><span class="sxs-lookup"><span data-stu-id="77787-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="77787-104">In questo argomento viene descritto come caricare immagini in Creazione di siti Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="77787-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="77787-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="77787-105">Overview</span></span>

<span data-ttu-id="77787-106">La libreria multimediale Creazione di siti Web Commerce consente di caricare le immagini, singolarmente o in blocco, utilizzando le cartelle.</span><span class="sxs-lookup"><span data-stu-id="77787-106">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="77787-107">È sempre necessario caricare la versione dell'immagine con la risoluzione e la qualità più alte, perché il componente di dimensionamento immagine ottimizza automaticamente l'immagine per essere adatta a diversi riquadri di visualizzazione e ai punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="77787-107">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="77787-108">Informazioni sull'immagine specificate durante il caricamento</span><span class="sxs-lookup"><span data-stu-id="77787-108">Image information specified during upload</span></span>

<span data-ttu-id="77787-109">Quando si carica un'immagine, è possibile specificare le seguenti informazioni.</span><span class="sxs-lookup"><span data-stu-id="77787-109">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="77787-110">**Titolo, testo alternativo, Descrizione, parole chiave**: i metadati dell'immagine o delle immagini.</span><span class="sxs-lookup"><span data-stu-id="77787-110">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="77787-111">Titolo e testo alternativo sono valori obbligatori.</span><span class="sxs-lookup"><span data-stu-id="77787-111">Title and alt text are required values.</span></span>
- <span data-ttu-id="77787-112">**Seleziona categoria**:</span><span class="sxs-lookup"><span data-stu-id="77787-112">**Select category**:</span></span>
    - <span data-ttu-id="77787-113">**Nessuna**: utilizzato per un'immagine o immagini di storytelling e-commerce.</span><span class="sxs-lookup"><span data-stu-id="77787-113">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="77787-114">**Prodotto, categoria, cliente, dipendente, catalogo**: usati per un'immagine o immagini omnicanale Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="77787-114">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="77787-115">**Pubblica risorse dopo il caricamento**: quando questa casella di controllo è selezionata, l'immagine o le immagini vengono pubblicate immediatamente dopo il caricamento.</span><span class="sxs-lookup"><span data-stu-id="77787-115">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="77787-116">Le risorse immagine con una categoria assegnata vengono inoltre automaticamente contrassegnate con la categoria come parola chiave per facilitare la ricerca di risorse di una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="77787-116">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="77787-117">Convenzioni di denominazione per immagini omnicanale</span><span class="sxs-lookup"><span data-stu-id="77787-117">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="77787-118">Se la libreria multimediale è stata configurata come backend dell'immagine omnicanale, è possibile utilizzare le categorie di immagini per indicare a quale categoria appartiene l'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="77787-118">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="77787-119">Esiste anche una convenzione di denominazione che deve essere seguita per garantire che le immagini vengano recuperate correttamente da altri canali, come il punto vendita (POS).</span><span class="sxs-lookup"><span data-stu-id="77787-119">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="77787-120">La convenzione di denominazione predefinita varia in base alla categoria:</span><span class="sxs-lookup"><span data-stu-id="77787-120">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="77787-121">Le immagini del catalogo devono essere denominate "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="77787-121">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="77787-122">Le immagini di categoria devono essere denominate "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="77787-122">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="77787-123">Le immagini dei clienti devono essere denominate "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="77787-123">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="77787-124">Le immagini dei dipendenti devono essere denominate "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="77787-124">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="77787-125">Le immagini dei prodotti devono essere denominate "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="77787-125">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="77787-126">001 è la sequenza dell'immagine e può essere 001, 002, 003, 004 o 005</span><span class="sxs-lookup"><span data-stu-id="77787-126">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="77787-127">Le immagini varianti dei prodotti devono essere denominate "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="77787-127">Product variant images should be named "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="77787-128">Caricare un'immagine</span><span class="sxs-lookup"><span data-stu-id="77787-128">Upload an image</span></span>

<span data-ttu-id="77787-129">Per caricare un'immagine in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="77787-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="77787-130">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="77787-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="77787-131">Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.</span><span class="sxs-lookup"><span data-stu-id="77787-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="77787-132">Nella finestra Esplora file, individuare e selezionare uno o più file immagine da caricare, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="77787-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="77787-133">Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.</span><span class="sxs-lookup"><span data-stu-id="77787-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="77787-134">Immettere una descrizione e le parole chiave facoltative e selezionare una categoria, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="77787-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="77787-135">Se si desidera pubblicare le immagini immediatamente dopo averle caricate, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="77787-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="77787-136">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="77787-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="77787-137">Caricare una cartella di immagini</span><span class="sxs-lookup"><span data-stu-id="77787-137">Upload a folder of images</span></span>

<span data-ttu-id="77787-138">Per caricare in blocco una cartella di immagini in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="77787-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="77787-139">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="77787-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="77787-140">Sulla barra dei comandi, selezionare **Carica \> Carica cartella**.</span><span class="sxs-lookup"><span data-stu-id="77787-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="77787-141">Nella finestra Esplora file, individuare e selezionare una cartella da caricare, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="77787-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="77787-142">Nella finestra di dialogo **Carica elementi multimediali**, inserire le parole chiave opzionali e selezionare una categoria, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="77787-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="77787-143">Se si desidera pubblicare le immagini nella cartella immediatamente dopo averla caricata, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="77787-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="77787-144">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="77787-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="77787-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="77787-145">Additional resources</span></span>

[<span data-ttu-id="77787-146">Panoramica della gestione risorse digitali</span><span class="sxs-lookup"><span data-stu-id="77787-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="77787-147">Caricare video</span><span class="sxs-lookup"><span data-stu-id="77787-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="77787-148">Caricare file</span><span class="sxs-lookup"><span data-stu-id="77787-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="77787-149">Tagliare immagini</span><span class="sxs-lookup"><span data-stu-id="77787-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="77787-150">Personalizzare punti focali immagine</span><span class="sxs-lookup"><span data-stu-id="77787-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="77787-151">Caricare e fornire file statici</span><span class="sxs-lookup"><span data-stu-id="77787-151">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]