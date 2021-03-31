---
title: Caricare file diversi da immagini e video
description: Questo argomento descrive come caricare file binari diversi da immagini e video in Creazione di siti Web Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c065aa961cf5c2d6770ae47c63a75953e6d38e00
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222539"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="94c09-103">Caricare file diversi da immagini e video</span><span class="sxs-lookup"><span data-stu-id="94c09-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="94c09-104">Questo argomento descrive come caricare file che non siano immagini e video in Creazione di siti Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="94c09-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="94c09-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="94c09-105">Overview</span></span>

<span data-ttu-id="94c09-106">La libreria multimediale Creazione di siti Web Commerce supporta il caricamento di risorse binarie diverse da immagini o video.</span><span class="sxs-lookup"><span data-stu-id="94c09-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="94c09-107">Ad esempio, si potrebbe voler caricare file Microsoft Excel, Microsoft Word, Microsoft PowerPoint o PDF.</span><span class="sxs-lookup"><span data-stu-id="94c09-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="94c09-108">Sono supportati i seguenti tipi di documento:</span><span class="sxs-lookup"><span data-stu-id="94c09-108">The following document types are supported:</span></span>
- <span data-ttu-id="94c09-109">7Z</span><span class="sxs-lookup"><span data-stu-id="94c09-109">7Z</span></span>
- <span data-ttu-id="94c09-110">AVI</span><span class="sxs-lookup"><span data-stu-id="94c09-110">AVI</span></span>
- <span data-ttu-id="94c09-111">CS</span><span class="sxs-lookup"><span data-stu-id="94c09-111">CS</span></span>
- <span data-ttu-id="94c09-112">CSS</span><span class="sxs-lookup"><span data-stu-id="94c09-112">CSS</span></span>
- <span data-ttu-id="94c09-113">DOC</span><span class="sxs-lookup"><span data-stu-id="94c09-113">DOC</span></span>
- <span data-ttu-id="94c09-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="94c09-114">DOCX</span></span>
- <span data-ttu-id="94c09-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="94c09-115">EPUB</span></span>
- <span data-ttu-id="94c09-116">GIF</span><span class="sxs-lookup"><span data-stu-id="94c09-116">GIF</span></span>
- <span data-ttu-id="94c09-117">INDD</span><span class="sxs-lookup"><span data-stu-id="94c09-117">INDD</span></span>
- <span data-ttu-id="94c09-118">JAR</span><span class="sxs-lookup"><span data-stu-id="94c09-118">JAR</span></span>
- <span data-ttu-id="94c09-119">JPG</span><span class="sxs-lookup"><span data-stu-id="94c09-119">JPG</span></span>
- <span data-ttu-id="94c09-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="94c09-120">JPEG</span></span>
- <span data-ttu-id="94c09-121">JS</span><span class="sxs-lookup"><span data-stu-id="94c09-121">JS</span></span>
- <span data-ttu-id="94c09-122">MP3</span><span class="sxs-lookup"><span data-stu-id="94c09-122">MP3</span></span>
- <span data-ttu-id="94c09-123">MP4</span><span class="sxs-lookup"><span data-stu-id="94c09-123">MP4</span></span>
- <span data-ttu-id="94c09-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="94c09-124">MPEG</span></span>
- <span data-ttu-id="94c09-125">MPG</span><span class="sxs-lookup"><span data-stu-id="94c09-125">MPG</span></span>
- <span data-ttu-id="94c09-126">ODP</span><span class="sxs-lookup"><span data-stu-id="94c09-126">ODP</span></span>
- <span data-ttu-id="94c09-127">ODS</span><span class="sxs-lookup"><span data-stu-id="94c09-127">ODS</span></span>
- <span data-ttu-id="94c09-128">ODT</span><span class="sxs-lookup"><span data-stu-id="94c09-128">ODT</span></span>
- <span data-ttu-id="94c09-129">PDF</span><span class="sxs-lookup"><span data-stu-id="94c09-129">PDF</span></span>
- <span data-ttu-id="94c09-130">PNG</span><span class="sxs-lookup"><span data-stu-id="94c09-130">PNG</span></span>
- <span data-ttu-id="94c09-131">PPT</span><span class="sxs-lookup"><span data-stu-id="94c09-131">PPT</span></span>
- <span data-ttu-id="94c09-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="94c09-132">PPTX</span></span>
- <span data-ttu-id="94c09-133">PS</span><span class="sxs-lookup"><span data-stu-id="94c09-133">PS</span></span>
- <span data-ttu-id="94c09-134">QXP</span><span class="sxs-lookup"><span data-stu-id="94c09-134">QXP</span></span>
- <span data-ttu-id="94c09-135">RAR</span><span class="sxs-lookup"><span data-stu-id="94c09-135">RAR</span></span>
- <span data-ttu-id="94c09-136">RTF</span><span class="sxs-lookup"><span data-stu-id="94c09-136">RTF</span></span>
- <span data-ttu-id="94c09-137">SVG</span><span class="sxs-lookup"><span data-stu-id="94c09-137">SVG</span></span>
- <span data-ttu-id="94c09-138">TAR</span><span class="sxs-lookup"><span data-stu-id="94c09-138">TAR</span></span>
- <span data-ttu-id="94c09-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="94c09-139">TGZ</span></span>
- <span data-ttu-id="94c09-140">TXT</span><span class="sxs-lookup"><span data-stu-id="94c09-140">TXT</span></span>
- <span data-ttu-id="94c09-141">WMV</span><span class="sxs-lookup"><span data-stu-id="94c09-141">WMV</span></span>
- <span data-ttu-id="94c09-142">XLS</span><span class="sxs-lookup"><span data-stu-id="94c09-142">XLS</span></span>
- <span data-ttu-id="94c09-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="94c09-143">XLSX</span></span>
- <span data-ttu-id="94c09-144">XML</span><span class="sxs-lookup"><span data-stu-id="94c09-144">XML</span></span>
- <span data-ttu-id="94c09-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="94c09-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="94c09-146">Carica un file</span><span class="sxs-lookup"><span data-stu-id="94c09-146">Upload a file</span></span>

<span data-ttu-id="94c09-147">Per caricare un file in Creazione di siti Web Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="94c09-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="94c09-148">Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="94c09-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="94c09-149">Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.</span><span class="sxs-lookup"><span data-stu-id="94c09-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="94c09-150">In Esplora file, selezionare uno o più file, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="94c09-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="94c09-151">Nella finestra di dialogo **Carica elemento multimediale**, immettere titolo, Descrizione e metadati delle parole chiave, se necessario.</span><span class="sxs-lookup"><span data-stu-id="94c09-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="94c09-152">Per pubblicare i file immediatamente dopo averli caricati, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.</span><span class="sxs-lookup"><span data-stu-id="94c09-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="94c09-153">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="94c09-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94c09-154">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="94c09-154">Additional resources</span></span>

[<span data-ttu-id="94c09-155">Panoramica della gestione risorse digitali</span><span class="sxs-lookup"><span data-stu-id="94c09-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="94c09-156">Caricare immagini</span><span class="sxs-lookup"><span data-stu-id="94c09-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="94c09-157">Caricare video</span><span class="sxs-lookup"><span data-stu-id="94c09-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="94c09-158">Tagliare immagini</span><span class="sxs-lookup"><span data-stu-id="94c09-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="94c09-159">Personalizzare punti focali immagine</span><span class="sxs-lookup"><span data-stu-id="94c09-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="94c09-160">Caricare e fornire file statici</span><span class="sxs-lookup"><span data-stu-id="94c09-160">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]