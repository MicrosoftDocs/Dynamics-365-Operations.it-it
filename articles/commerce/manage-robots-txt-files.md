---
title: Gestire i file robots.txt
description: Questo argomento descrive come gestire i file robots.txt in Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: afd7982179dc9845c9adc24e8c7c9951a04460a3
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477710"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="8f11a-103">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="8f11a-103">Manage robots.txt files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8f11a-104">Questo argomento descrive come gestire i file robots.txt in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f11a-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8f11a-105">Lo standard di esclusione dei robot, o robots.txt, è uno standard utilizzato dai siti Web per comunicare con i robot Web.</span><span class="sxs-lookup"><span data-stu-id="8f11a-105">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="8f11a-106">Indica ai robot Web le aree di un sito Web che non devono essere visitate.</span><span class="sxs-lookup"><span data-stu-id="8f11a-106">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="8f11a-107">I robot vengono spesso utilizzati dai motori di ricerca per indicizzare i siti Web.</span><span class="sxs-lookup"><span data-stu-id="8f11a-107">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="8f11a-108">Per escludere i robot da un server, si crea un file sul server.</span><span class="sxs-lookup"><span data-stu-id="8f11a-108">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="8f11a-109">In questo file, si specificano i criteri di accesso per i robot.</span><span class="sxs-lookup"><span data-stu-id="8f11a-109">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="8f11a-110">Il file deve essere accessibile tramite HTTP all'URL locale **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8f11a-110">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="8f11a-111">Il file robots.txt aiuta i motori di ricerca a indicizzare il contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="8f11a-111">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="8f11a-112">Dynamics 365 Commerce consente di caricare un file robots.txt per il dominio.</span><span class="sxs-lookup"><span data-stu-id="8f11a-112">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="8f11a-113">Per ogni dominio nell'ambiente Commerce, è possibile caricare un file robots.txt e associarlo a quel dominio.</span><span class="sxs-lookup"><span data-stu-id="8f11a-113">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="8f11a-114">Per ulteriori informazioni sul file robots.txt, visitare [Le pagine dei robot Web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="8f11a-114">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="8f11a-115">Caricare un file robots.txt</span><span class="sxs-lookup"><span data-stu-id="8f11a-115">Upload a robots.txt file</span></span>

<span data-ttu-id="8f11a-116">Dopo aver creato e modificato il file robots.txt in base allo [standard di esclusione dei robot](https://www.robotstxt.org/orig.html), assicurarsi che il file sia accessibile sul computer in cui verranno utilizzati gli strumenti di creazione di Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f11a-116">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="8f11a-117">Il file deve essere denominato **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8f11a-117">The file must be named **robots.txt**.</span></span> <span data-ttu-id="8f11a-118">Per risultati ottimali, deve essere nel formato indicato nello standard.</span><span class="sxs-lookup"><span data-stu-id="8f11a-118">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="8f11a-119">Ogni cliente Commerce è responsabile della convalida e della manutenzione dei contenuti del suo file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8f11a-119">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="8f11a-120">Per caricare un file robots.txt, è necessario effettuare l'accesso a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f11a-120">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="8f11a-121">Per caricare un file robots.txt in Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f11a-121">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8f11a-122">Accedere a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f11a-122">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="8f11a-123">Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="8f11a-123">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="8f11a-124">Sotto **Impostazioni tenant**, selezionare **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8f11a-124">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="8f11a-125">Un elenco di tutti i domini associati all'ambiente appare nella parte principale della finestra.</span><span class="sxs-lookup"><span data-stu-id="8f11a-125">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="8f11a-126">Selezionare **Gestisci** per caricare un file robots.txt per un dominio nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8f11a-126">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="8f11a-127">Nel menu a destra, selezionare il pulsante **Carica** (la freccia rivolta verso l'alto) accanto al dominio associato al file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8f11a-127">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="8f11a-128">Viene visualizzata una finestra di dialogo del browser di file.</span><span class="sxs-lookup"><span data-stu-id="8f11a-128">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="8f11a-129">Nella finestra di dialogo, individuare e selezionare il file robots.txt che si desidera caricare per il dominio associato, quindi selezionare **Apri** per completare il caricamento.</span><span class="sxs-lookup"><span data-stu-id="8f11a-129">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="8f11a-130">Durante il caricamento, Commerce verifica che il file sia un file di testo, ma non convalida il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="8f11a-130">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="8f11a-131">Scaricare un file robots.txt</span><span class="sxs-lookup"><span data-stu-id="8f11a-131">Download a robots.txt file</span></span>

<span data-ttu-id="8f11a-132">Per scaricare un file robots.txt in Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f11a-132">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8f11a-133">Accedere a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f11a-133">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="8f11a-134">Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="8f11a-134">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="8f11a-135">Sotto **Impostazioni tenant**, selezionare **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8f11a-135">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="8f11a-136">Un elenco di tutti i domini associati all'ambiente appare nella parte principale della finestra.</span><span class="sxs-lookup"><span data-stu-id="8f11a-136">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="8f11a-137">Selezionare **Gestisci** per scaricare un file robots.txt per un dominio nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8f11a-137">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="8f11a-138">Nel menu a destra, selezionare il pulsante **Scarica** (la freccia rivolta verso il basso) accanto al dominio associato al file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8f11a-138">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="8f11a-139">Viene visualizzata una finestra di dialogo del browser di file.</span><span class="sxs-lookup"><span data-stu-id="8f11a-139">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="8f11a-140">Nella finestra di dialogo, andare alla posizione desiderata sull'unità locale, confermare o inserire un nome file e quindi selezionare **Salva** per completare il download.</span><span class="sxs-lookup"><span data-stu-id="8f11a-140">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="8f11a-141">Questa procedura può essere utilizzata per scaricare solo i file robots.txt precedentemente caricati tramite gli strumenti di creazione di Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f11a-141">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="8f11a-142">Eliminare un file robots.txt</span><span class="sxs-lookup"><span data-stu-id="8f11a-142">Delete a robots.txt file</span></span>

<span data-ttu-id="8f11a-143">Per eliminare un file robots.txt in Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f11a-143">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8f11a-144">Accedere a Commerce come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f11a-144">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="8f11a-145">Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="8f11a-145">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="8f11a-146">Sotto **Impostazioni tenant**, selezionare **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8f11a-146">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="8f11a-147">Un elenco di tutti i domini associati all'ambiente appare nella parte principale della finestra.</span><span class="sxs-lookup"><span data-stu-id="8f11a-147">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="8f11a-148">Selezionare **Gestisci** per eliminare un file robots.txt per un dominio nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8f11a-148">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="8f11a-149">Nel menu a destra, selezionare il pulsante **Elimina** (il simbolo del cestino) accanto al dominio associato al file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8f11a-149">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="8f11a-150">Viene visualizzata una finestra del browser di file.</span><span class="sxs-lookup"><span data-stu-id="8f11a-150">A file browser window appears.</span></span>
6. <span data-ttu-id="8f11a-151">Nella finestra del browser di file, individuare e selezionare il file robots.txt che si desidera eliminare per il dominio, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8f11a-151">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="8f11a-152">Viene visualizzata una finestra di messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="8f11a-152">A warning message box appears.</span></span>
7. <span data-ttu-id="8f11a-153">Nella finestra del messaggio, selezionare **Elimina** per confermare l'eliminazione del file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8f11a-153">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="8f11a-154">Questa procedura può essere utilizzata per eliminare solo i file robots.txt precedentemente caricati tramite gli strumenti di creazione di Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f11a-154">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f11a-155">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8f11a-155">Additional resources</span></span>

[<span data-ttu-id="8f11a-156">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="8f11a-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="8f11a-157">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="8f11a-157">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="8f11a-158">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="8f11a-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="8f11a-159">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="8f11a-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="8f11a-160">Caricare reindirizzamenti URL in blocco</span><span class="sxs-lookup"><span data-stu-id="8f11a-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="8f11a-161">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="8f11a-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="8f11a-162">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="8f11a-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="8f11a-163">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="8f11a-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="8f11a-164">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="8f11a-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="8f11a-165">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="8f11a-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
