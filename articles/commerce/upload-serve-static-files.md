---
title: Caricare e utilizzare file statici
description: Questo argomento descrive come caricare un file statico nel generatore di siti di Microsoft Dynamics 365 Commerce e come creare un URL e un nome file personalizzati che possono essere utilizzati per richiedere quel file.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: aba9dde2ed9d5fa09e92fcdd784a53f208930eda
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211021"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="e6a0d-103">Caricare e utilizzare file statici</span><span class="sxs-lookup"><span data-stu-id="e6a0d-103">Upload and serve static files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e6a0d-104">Questo argomento descrive come caricare un file statico nel generatore di siti di Microsoft Dynamics 365 Commerce e come creare un URL e un nome file personalizzati che possono essere utilizzati per richiedere quel file.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="e6a0d-105">Alcuni connettori di terze parti richiedono che un file sia ospitato e servito dal sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="e6a0d-106">Questi connettori prevedono che il file venga restituito dalle richieste in un percorso URL di callback e un nome file specifici.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="e6a0d-107">Pertanto, questo argomento spiega come caricare e servire un file statico con un URL e un nome file definibili dall'utente in un sito di e-commerce di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="e6a0d-108">Crea un URL del sito che restituisca un file statico</span><span class="sxs-lookup"><span data-stu-id="e6a0d-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="e6a0d-109">Per creare un URL del sito che restituisce un file statico nel generatore di siti di Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="e6a0d-110">Andare alla libreria multimediale del sito e caricare il file che deve essere servito dalle richieste all'URL che verrà definito.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="e6a0d-111">Se è già stato caricato il file, è possibile saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="e6a0d-112">Andare a **URL** per il sito.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="e6a0d-113">Selezionare **Nuovo \> Nuovo URL**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="e6a0d-114">Nella finestra di dialogo **Nuovo URL**, selezionare **Risorsa libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="e6a0d-115">Nel campo **Percorso URL** inserire il percorso dell'URL.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="e6a0d-116">Includere il nome del file nel percorso.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="e6a0d-117">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-117">Select **Next**.</span></span> <span data-ttu-id="e6a0d-118">La libreria multimediale viene aperta e mostra tutte le risorse multimediali di tipo **documento** che sono state caricate.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="e6a0d-119">Seleziona il file che deve essere servito per le richieste all'URL definito nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="e6a0d-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-120">Select **Save**.</span></span>

<span data-ttu-id="e6a0d-121">A questo punto, l'URL creato è in stato bozza.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="e6a0d-122">Il file a cui punta l'URL non verrà restituito finché non si pubblica l'URL.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="e6a0d-123">Prima di pubblicare l'URL, è possibile verificare che restituisca i dati corretti.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="e6a0d-124">Convalidare e pubblicare un URL</span><span class="sxs-lookup"><span data-stu-id="e6a0d-124">Validate and publish a URL</span></span>

<span data-ttu-id="e6a0d-125">Per convalidare un URL prima di pubblicarlo, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="e6a0d-126">Andare a **URL** per il sito e selezionare l'URL da visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="e6a0d-127">Nel riquadro delle proprietà a destra, sotto il pulsante **Modifica** selezionare il collegamento URL corretto.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="e6a0d-128">Si apre una nuova finestra del browser e viene visualizzato un errore 404.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="e6a0d-129">Aggiungere la stringa di query **?preview=inprogress** all'URL (ad esempio, `https://yoursite.com/callback.html?preview=inprogress`) e ricaricare la pagina.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="e6a0d-130">Il file caricato nella libreria multimediale viene restituito nella risposta.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="e6a0d-131">Dopo aver convalidato l'URL, è possibile pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="e6a0d-132">Andare a **URL** per il sito e selezionare l'URL.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="e6a0d-133">Nella barra dei comandi selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="e6a0d-134">Aggiornare il file a cui punta un URL</span><span class="sxs-lookup"><span data-stu-id="e6a0d-134">Update the file that a URL points to</span></span>

<span data-ttu-id="e6a0d-135">Dopo che un URL è stato pubblicato, è possibile aggiornarlo in modo che punti a un file diverso.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="e6a0d-136">In alternativa, è possibile aggiornare l'URL in modo che punti a un diverso tipo di risorsa, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="e6a0d-137">Ad esempio, è possibile puntare l'URL a una pagina interna o a un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="e6a0d-138">Per aggiornare il file a cui punta un URL, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="e6a0d-139">Andare a **URL** per il sito e selezionare l'URL da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="e6a0d-140">Nel riquadro delle proprietà a destra, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="e6a0d-141">Sotto **Assegnazione URL**, selezionare la casella **Passaggio 2** quindi selezionare un nuovo documento dalla libreria multimediale.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="e6a0d-142">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="e6a0d-143">Aggiornare il tipo di risorsa a cui punta un URL</span><span class="sxs-lookup"><span data-stu-id="e6a0d-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="e6a0d-144">È anche possibile aggiornare un URL in modo che punti a un diverso tipo di risorsa (asset), come una pagina interna o un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="e6a0d-145">Per aggiornare il tipo di risorsa a cui punta un URL, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="e6a0d-146">Andare a **URL** per il sito e selezionare l'URL da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="e6a0d-147">Nel riquadro delle proprietà a destra, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="e6a0d-148">Sotto **Assegnazione URL**, sotto **Passaggio 1**, selezionare un altro tipo di risorsa.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="e6a0d-149">Selezionare la casella **Passaggio 2** quindi selezionare la nuova risorsa.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="e6a0d-150">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="e6a0d-151">Modificare il percorso dell'URL</span><span class="sxs-lookup"><span data-stu-id="e6a0d-151">Change the URL path</span></span>

<span data-ttu-id="e6a0d-152">Dopo aver creato un URL, il suo percorso non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="e6a0d-153">Se è necessario modificare il percorso dell'URL che serve un file o qualsiasi altro tipo di risorsa, è necessario creare un nuovo URL, mapparlo al file esistente o un'altra risorsa, quindi annullare la pubblicazione ed eliminare il vecchio URL.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="e6a0d-154">Per modificare il percorso dell'URL, eseguire le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="e6a0d-155">Per creare un nuovo URL e mapparlo al file esistente o a un'altra risorsa, seguire le istruzioni nella precedente sezione [Creare un URL del sito che restituisca un file statico](#create-a-site-url-that-returns-a-static-file) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="e6a0d-156">Selezionare il nuovo URL e selezionare **Pubblica** sulla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="e6a0d-157">Il nuovo URL viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-157">The new URL is published.</span></span>
1. <span data-ttu-id="e6a0d-158">Per annullare la pubblicazione del vecchio URL, selezionalo, quindi selezionare **Annulla pubblicazione** sulla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="e6a0d-159">È possibile ora eliminare il vecchio URL se si desidera.</span><span class="sxs-lookup"><span data-stu-id="e6a0d-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6a0d-160">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e6a0d-160">Additional resources</span></span>

[<span data-ttu-id="e6a0d-161">Panoramica della gestione cespiti digitali</span><span class="sxs-lookup"><span data-stu-id="e6a0d-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="e6a0d-162">Caricare immagini</span><span class="sxs-lookup"><span data-stu-id="e6a0d-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="e6a0d-163">Caricare i video</span><span class="sxs-lookup"><span data-stu-id="e6a0d-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="e6a0d-164">Caricare file diversi da immagini e video</span><span class="sxs-lookup"><span data-stu-id="e6a0d-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="e6a0d-165">Tagliare immagini</span><span class="sxs-lookup"><span data-stu-id="e6a0d-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="e6a0d-166">Personalizzare punti focali immagine</span><span class="sxs-lookup"><span data-stu-id="e6a0d-166">Customize image focal points</span></span>](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]