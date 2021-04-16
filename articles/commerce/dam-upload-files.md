---
title: Caricare file diversi da immagini e video
description: Questo argomento descrive come caricare file binari diversi da immagini e video in Creazione di siti Web Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799255"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="3d0bb-103">Caricare file diversi da immagini e video</span><span class="sxs-lookup"><span data-stu-id="3d0bb-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3d0bb-104">Questo argomento descrive come caricare file che non siano immagini e video in Creazione di siti Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="3d0bb-105">La libreria multimediale Creazione di siti Web Commerce supporta il caricamento di risorse binarie diverse da immagini o video.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="3d0bb-106">Ad esempio, si potrebbe voler caricare file Microsoft Excel, Microsoft Word, Microsoft PowerPoint o PDF.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="3d0bb-107">Sono supportati i seguenti tipi di documento:</span><span class="sxs-lookup"><span data-stu-id="3d0bb-107">The following document types are supported:</span></span>
- <span data-ttu-id="3d0bb-108">7Z</span><span class="sxs-lookup"><span data-stu-id="3d0bb-108">7Z</span></span>
- <span data-ttu-id="3d0bb-109">AVI</span><span class="sxs-lookup"><span data-stu-id="3d0bb-109">AVI</span></span>
- <span data-ttu-id="3d0bb-110">CS</span><span class="sxs-lookup"><span data-stu-id="3d0bb-110">CS</span></span>
- <span data-ttu-id="3d0bb-111">CSS</span><span class="sxs-lookup"><span data-stu-id="3d0bb-111">CSS</span></span>
- <span data-ttu-id="3d0bb-112">DOC</span><span class="sxs-lookup"><span data-stu-id="3d0bb-112">DOC</span></span>
- <span data-ttu-id="3d0bb-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="3d0bb-113">DOCX</span></span>
- <span data-ttu-id="3d0bb-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="3d0bb-114">EPUB</span></span>
- <span data-ttu-id="3d0bb-115">GIF</span><span class="sxs-lookup"><span data-stu-id="3d0bb-115">GIF</span></span>
- <span data-ttu-id="3d0bb-116">INDD</span><span class="sxs-lookup"><span data-stu-id="3d0bb-116">INDD</span></span>
- <span data-ttu-id="3d0bb-117">JAR</span><span class="sxs-lookup"><span data-stu-id="3d0bb-117">JAR</span></span>
- <span data-ttu-id="3d0bb-118">JPG</span><span class="sxs-lookup"><span data-stu-id="3d0bb-118">JPG</span></span>
- <span data-ttu-id="3d0bb-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="3d0bb-119">JPEG</span></span>
- <span data-ttu-id="3d0bb-120">JS</span><span class="sxs-lookup"><span data-stu-id="3d0bb-120">JS</span></span>
- <span data-ttu-id="3d0bb-121">MP3</span><span class="sxs-lookup"><span data-stu-id="3d0bb-121">MP3</span></span>
- <span data-ttu-id="3d0bb-122">MP4</span><span class="sxs-lookup"><span data-stu-id="3d0bb-122">MP4</span></span>
- <span data-ttu-id="3d0bb-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="3d0bb-123">MPEG</span></span>
- <span data-ttu-id="3d0bb-124">MPG</span><span class="sxs-lookup"><span data-stu-id="3d0bb-124">MPG</span></span>
- <span data-ttu-id="3d0bb-125">ODP</span><span class="sxs-lookup"><span data-stu-id="3d0bb-125">ODP</span></span>
- <span data-ttu-id="3d0bb-126">ODS</span><span class="sxs-lookup"><span data-stu-id="3d0bb-126">ODS</span></span>
- <span data-ttu-id="3d0bb-127">ODT</span><span class="sxs-lookup"><span data-stu-id="3d0bb-127">ODT</span></span>
- <span data-ttu-id="3d0bb-128">PDF</span><span class="sxs-lookup"><span data-stu-id="3d0bb-128">PDF</span></span>
- <span data-ttu-id="3d0bb-129">PNG</span><span class="sxs-lookup"><span data-stu-id="3d0bb-129">PNG</span></span>
- <span data-ttu-id="3d0bb-130">PPT</span><span class="sxs-lookup"><span data-stu-id="3d0bb-130">PPT</span></span>
- <span data-ttu-id="3d0bb-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="3d0bb-131">PPTX</span></span>
- <span data-ttu-id="3d0bb-132">PS</span><span class="sxs-lookup"><span data-stu-id="3d0bb-132">PS</span></span>
- <span data-ttu-id="3d0bb-133">QXP</span><span class="sxs-lookup"><span data-stu-id="3d0bb-133">QXP</span></span>
- <span data-ttu-id="3d0bb-134">RAR</span><span class="sxs-lookup"><span data-stu-id="3d0bb-134">RAR</span></span>
- <span data-ttu-id="3d0bb-135">RTF</span><span class="sxs-lookup"><span data-stu-id="3d0bb-135">RTF</span></span>
- <span data-ttu-id="3d0bb-136">SVG</span><span class="sxs-lookup"><span data-stu-id="3d0bb-136">SVG</span></span>
- <span data-ttu-id="3d0bb-137">TAR</span><span class="sxs-lookup"><span data-stu-id="3d0bb-137">TAR</span></span>
- <span data-ttu-id="3d0bb-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="3d0bb-138">TGZ</span></span>
- <span data-ttu-id="3d0bb-139">TXT</span><span class="sxs-lookup"><span data-stu-id="3d0bb-139">TXT</span></span>
- <span data-ttu-id="3d0bb-140">WMV</span><span class="sxs-lookup"><span data-stu-id="3d0bb-140">WMV</span></span>
- <span data-ttu-id="3d0bb-141">XLS</span><span class="sxs-lookup"><span data-stu-id="3d0bb-141">XLS</span></span>
- <span data-ttu-id="3d0bb-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="3d0bb-142">XLSX</span></span>
- <span data-ttu-id="3d0bb-143">XML</span><span class="sxs-lookup"><span data-stu-id="3d0bb-143">XML</span></span>
- <span data-ttu-id="3d0bb-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="3d0bb-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="3d0bb-145">Carica un file</span><span class="sxs-lookup"><span data-stu-id="3d0bb-145">Upload a file</span></span>

<span data-ttu-id="3d0bb-146">Per caricare un file in Creazione di siti Web Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3d0bb-147">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="3d0bb-148">Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="3d0bb-149">In Esplora file, selezionare uno o più file, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="3d0bb-150">Nella finestra di dialogo **Carica elemento multimediale**, immettere titolo, Descrizione e metadati delle parole chiave, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="3d0bb-151">Per pubblicare i file immediatamente dopo averli caricati, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="3d0bb-152">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d0bb-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d0bb-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3d0bb-153">Additional resources</span></span>

[<span data-ttu-id="3d0bb-154">Panoramica della gestione risorse digitali</span><span class="sxs-lookup"><span data-stu-id="3d0bb-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="3d0bb-155">Caricare immagini</span><span class="sxs-lookup"><span data-stu-id="3d0bb-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="3d0bb-156">Caricare video</span><span class="sxs-lookup"><span data-stu-id="3d0bb-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="3d0bb-157">Tagliare immagini</span><span class="sxs-lookup"><span data-stu-id="3d0bb-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="3d0bb-158">Personalizzare punti focali immagine</span><span class="sxs-lookup"><span data-stu-id="3d0bb-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="3d0bb-159">Caricare e fornire file statici</span><span class="sxs-lookup"><span data-stu-id="3d0bb-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
