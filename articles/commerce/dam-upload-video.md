---
title: Caricare i video
description: In questo argomento viene descritto come caricare i video in Creazione di siti Web Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5ec20f8caee2f5a62230be05923dfd52600c1e35
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799207"
---
# <a name="upload-videos"></a><span data-ttu-id="7c86e-103">Caricare i video</span><span class="sxs-lookup"><span data-stu-id="7c86e-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7c86e-104">In questo argomento viene descritto come caricare i video in Creazione di siti Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7c86e-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="7c86e-105">La libreria multimediale Creazione di siti Web Commerce consente di caricare i video.</span><span class="sxs-lookup"><span data-stu-id="7c86e-105">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="7c86e-106">È sempre necessario caricare la versione di un video con il bitrate e la risoluzione più alti, perché il video verrà automaticamente convertito per essere adatto a diversi riquadri di visualizzazione e ai punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="7c86e-106">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="7c86e-107">Informazioni sul video specificate durante il caricamento</span><span class="sxs-lookup"><span data-stu-id="7c86e-107">Video information specified during upload</span></span>

<span data-ttu-id="7c86e-108">Quando si carica un video, è possibile specificare le seguenti informazioni.</span><span class="sxs-lookup"><span data-stu-id="7c86e-108">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="7c86e-109">**Titolo, Descrizione, parole chiave**: i metadati del video.</span><span class="sxs-lookup"><span data-stu-id="7c86e-109">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="7c86e-110">**Genera automaticamente sottotitoli**: specifica se i sottotitoli devono essere generati automaticamente per il video.</span><span class="sxs-lookup"><span data-stu-id="7c86e-110">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="7c86e-111">**Sottotitolo**: specifica i sottotitoli da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7c86e-111">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="7c86e-112">**Audio normale**: specifica la traccia audio normale da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7c86e-112">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="7c86e-113">**Anteprima**: specifica l'anteprima per il video.</span><span class="sxs-lookup"><span data-stu-id="7c86e-113">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="7c86e-114">Se non specificata, verrà generata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7c86e-114">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="7c86e-115">**Audio descrittivo**: specifica la traccia audio descrittivo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7c86e-115">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="7c86e-116">Caricare un video</span><span class="sxs-lookup"><span data-stu-id="7c86e-116">Upload a video</span></span>

<span data-ttu-id="7c86e-117">Per caricare un video in Creazione di siti Web, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="7c86e-117">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="7c86e-118">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="7c86e-118">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="7c86e-119">Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.</span><span class="sxs-lookup"><span data-stu-id="7c86e-119">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="7c86e-120">Nella finestra Esplora file, individuare e selezionare uno o più file video da caricare, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="7c86e-120">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="7c86e-121">Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.</span><span class="sxs-lookup"><span data-stu-id="7c86e-121">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="7c86e-122">Immettere una descrizione e le parole chiave facoltative e selezionare una categoria, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="7c86e-122">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="7c86e-123">Se si desidera pubblicare le immagini immediatamente dopo averle caricate, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**</span><span class="sxs-lookup"><span data-stu-id="7c86e-123">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="7c86e-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c86e-124">Select **OK**.</span></span>

<span data-ttu-id="7c86e-125">Se si stanno caricando più tipi di risorse contemporaneamente (ad esempio, immagini e video), nella finestra di dialogo **Carica elemento multimediale** sarà possibile specificare solo parole chiave, se i file devono essere pubblicati immediatamente dopo il caricamento e se i sottotitoli devono essere generati automaticamente per i file video.</span><span class="sxs-lookup"><span data-stu-id="7c86e-125">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="7c86e-126">Tutte le risorse condivideranno le stesse parole chiave.</span><span class="sxs-lookup"><span data-stu-id="7c86e-126">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c86e-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7c86e-127">Additional resources</span></span>

[<span data-ttu-id="7c86e-128">Panoramica della gestione risorse digitali</span><span class="sxs-lookup"><span data-stu-id="7c86e-128">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="7c86e-129">Caricare immagini</span><span class="sxs-lookup"><span data-stu-id="7c86e-129">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="7c86e-130">Caricare file</span><span class="sxs-lookup"><span data-stu-id="7c86e-130">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="7c86e-131">Tagliare immagini</span><span class="sxs-lookup"><span data-stu-id="7c86e-131">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="7c86e-132">Personalizzare punti focali immagine</span><span class="sxs-lookup"><span data-stu-id="7c86e-132">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="7c86e-133">Caricare e fornire file statici</span><span class="sxs-lookup"><span data-stu-id="7c86e-133">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
