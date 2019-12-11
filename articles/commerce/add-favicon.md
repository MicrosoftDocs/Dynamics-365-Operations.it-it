---
title: Aggiungere una favicon
description: In questo argomento viene descritto come aggiungere un favicon al sito.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 58cb6c592351a96876532ef53d5d477ff93fafa1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696993"
---
# <a name="add-a-favicon"></a><span data-ttu-id="ba936-103">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="ba936-103">Add a favicon</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ba936-104">In questo argomento viene descritto come aggiungere un favicon al sito.</span><span class="sxs-lookup"><span data-stu-id="ba936-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="ba936-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ba936-105">Overview</span></span>

<span data-ttu-id="ba936-106">Un favicon è un piccolo file di grafica che viene visualizzato, tra l'altro, in una scheda del browser Web, nella barra degli indirizzi, nella cronologia delle esplorazioni e in segnalibri o preferiti.</span><span class="sxs-lookup"><span data-stu-id="ba936-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="ba936-107">È consigliabile aggiungere un favicon al sito, poiché rappresenta e rinforza il marchio e consente di differenziare il proprio sito da altri siti visitati dai clienti.</span><span class="sxs-lookup"><span data-stu-id="ba936-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="ba936-108">Sebbene sia possibile aggiungere più favicon di varie dimensioni e tipi di file al sito, in questo argomento viene descritto coma aggiungere un singolo favicon.</span><span class="sxs-lookup"><span data-stu-id="ba936-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="ba936-109">Tuttavia, lo stesso processo e la stessa posizione sono utilizzati per aggiungere più favicon.</span><span class="sxs-lookup"><span data-stu-id="ba936-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="ba936-110">Caricare un favicon nella raccolta di asset del sito</span><span class="sxs-lookup"><span data-stu-id="ba936-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="ba936-111">Per caricare un favicon nella raccolta di asset del sito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="ba936-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="ba936-112">Scegliere **Asset \> Carica \> Carica asset**.</span><span class="sxs-lookup"><span data-stu-id="ba936-112">Go to **Assets \> Upload \> Upload assets**.</span></span>
1. <span data-ttu-id="ba936-113">Trovare e selezionare il favicon nel file system locale.</span><span class="sxs-lookup"><span data-stu-id="ba936-113">Find and select the favicon on your local file system.</span></span>
1. <span data-ttu-id="ba936-114">Immettere un titolo e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba936-114">Enter a title, and then select **OK**.</span></span> 
1. <span data-ttu-id="ba936-115">Nel riquadro delle proprietà a destra, copiare l'URL pubblico del favicon.</span><span class="sxs-lookup"><span data-stu-id="ba936-115">In the property pane on the right, copy the public URL of the favicon.</span></span>

> [!NOTE]
> <span data-ttu-id="ba936-116">Se non si seleziona l'opzione **Pubblica asset dopo caricamento**, è necessario tornare alla pagina **Cespiti** e pubblicare manualmente il favicon in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="ba936-116">If you don't select the **Publish assets after upload** option, you must return to **Assets** page and manually publish the favicon later.</span></span>

## <a name="create-the-html-for-the-favicon"></a><span data-ttu-id="ba936-117">Creare il codice HTML per il favicon</span><span class="sxs-lookup"><span data-stu-id="ba936-117">Create the HTML for the favicon</span></span>

<span data-ttu-id="ba936-118">Per creare il codice HTML per il favicon, utilizzare il seguente frammento HTML.</span><span class="sxs-lookup"><span data-stu-id="ba936-118">To create the HTML for the favicon, use the following HTML snippet.</span></span> <span data-ttu-id="ba936-119">Per l'attributo **href**, sostituire **"URL\_pubblico\_per\_il\_favicon"** con l'URL pubblico copiato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ba936-119">For the **href** attribute, replace **"Public\_URL\_for\_your\_favicon"** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a><span data-ttu-id="ba936-120">Aggiungere il codice HTML per il favicon all'elemento \<intestazione\> delle pagine</span><span class="sxs-lookup"><span data-stu-id="ba936-120">Add the HTML for the favicon to the \<head\> element of your pages</span></span>

<span data-ttu-id="ba936-121">Per aggiungere un favicon al sito, utilizzare la stessa procedura utilizzata per aggiungere qualsiasi tipo di codice HTML o script all'elemento **\<intestazione\>** delle pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="ba936-121">To add a favicon to your site, use the same procedure that is used to add any type of HTML or script to the **\<head\>** element of your site pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba936-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ba936-122">Additional resources</span></span>

[<span data-ttu-id="ba936-123">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="ba936-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="ba936-124">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="ba936-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="ba936-125">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="ba936-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="ba936-126">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="ba936-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="ba936-127">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="ba936-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="ba936-128">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="ba936-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

