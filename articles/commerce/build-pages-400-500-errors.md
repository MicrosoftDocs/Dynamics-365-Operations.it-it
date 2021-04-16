---
title: Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx
description: In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799651"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="ed589-103">Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="ed589-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ed589-104">In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed589-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ed589-105">Se una richiesta non ha esito positivo, il server genera risposte per errori di codice stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="ed589-105">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="ed589-106">Il codice stato 404 viene acquisito e restituito se una pagina non è presente e il codice stato 500 viene acquisito e restituito in caso di errore nel server.</span><span class="sxs-lookup"><span data-stu-id="ed589-106">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="ed589-107">In Dynamics 365 Commerce, gli utenti dell'applicazione possono creare pagine di risposte per errori di codice stato che sono visibili agli utenti per tali risposte.</span><span class="sxs-lookup"><span data-stu-id="ed589-107">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="ed589-108">Creare una pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="ed589-108">Build a status code error response page</span></span>

<span data-ttu-id="ed589-109">Per iniziare a creare una pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ed589-109">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="ed589-110">Nel Web browser preferito, accedere a Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed589-110">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="ed589-111">Selezionare il sito per il quale si desidera creare una pagina di risposte per errori di codice stato 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="ed589-111">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="ed589-112">Creare il modello</span><span class="sxs-lookup"><span data-stu-id="ed589-112">Build the template</span></span>

<span data-ttu-id="ed589-113">Per creare il modello per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ed589-113">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="ed589-114">Andare a **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="ed589-114">Go to **Templates**.</span></span>
1. <span data-ttu-id="ed589-115">Selezionare **Nuovo** per creare un modello di pagina.</span><span class="sxs-lookup"><span data-stu-id="ed589-115">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="ed589-116">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per il nuovo modello e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed589-116">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="ed589-117">Creare il modello in base alla struttura che la pagina di risposte per errori di codice stato deve avere.</span><span class="sxs-lookup"><span data-stu-id="ed589-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="ed589-118">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="ed589-118">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="ed589-119">Creare la pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="ed589-119">Build the status code error response page</span></span>

<span data-ttu-id="ed589-120">Per creare la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ed589-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="ed589-121">Andare a **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="ed589-121">Go to **Pages**.</span></span>
1. <span data-ttu-id="ed589-122">Selezionare **Nuovo** per creare una pagina.</span><span class="sxs-lookup"><span data-stu-id="ed589-122">Select **New** to create a page.</span></span>
1. <span data-ttu-id="ed589-123">Nella finestra di dialogo **Scegli un modello**, selezionare un modello, quindi in **Nome pagina**, inserire un nome per la pagina di risposta dell'errore del codice di stato.</span><span class="sxs-lookup"><span data-stu-id="ed589-123">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="ed589-124">Lasciare vuoto il campo **URL pagina**.</span><span class="sxs-lookup"><span data-stu-id="ed589-124">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="ed589-125">Creare la pagina.</span><span class="sxs-lookup"><span data-stu-id="ed589-125">Build the page.</span></span>
1. <span data-ttu-id="ed589-126">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="ed589-126">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="ed589-127">È possibile creare pagine di risposte per errori di codice stato 4xx e 5xx.</span><span class="sxs-lookup"><span data-stu-id="ed589-127">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="ed589-128">In alternativa, è possibile utilizzare la stessa pagina di risposte per errori di codice stato per entrambe le categorie di errore.</span><span class="sxs-lookup"><span data-stu-id="ed589-128">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="ed589-129">Impostare un reindirizzamento per la pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="ed589-129">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="ed589-130">Per impostare un reindirizzamento per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ed589-130">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="ed589-131">Andare a **URL \> Nuovo \> Nuovo alias** e selezionare la pagina di risposte per errori di codice stato creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ed589-131">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="ed589-132">Nel campo **Alias**, immettere **default-4xx** o **default-5xx**, a seconda della pagina di risposte di errore di codice stato per la quale si sta impostando un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="ed589-132">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="ed589-133">Questi alias devono essere pubblicati.</span><span class="sxs-lookup"><span data-stu-id="ed589-133">These aliases must be published.</span></span> <span data-ttu-id="ed589-134">In caso contrario, il reindirizzamento non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="ed589-134">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="ed589-135">Selezionare **OK** per eseguire il commit del collegamento.</span><span class="sxs-lookup"><span data-stu-id="ed589-135">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="ed589-136">Se si utilizza una singola pagina di risposte per errori di codice stato per entrambe le categorie di errore, ripetere questa procedura per collegare un alias per l'altra categoria di errore alla stessa pagina.</span><span class="sxs-lookup"><span data-stu-id="ed589-136">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed589-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ed589-137">Additional resources</span></span>

[<span data-ttu-id="ed589-138">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="ed589-138">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="ed589-139">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="ed589-139">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="ed589-140">Creare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="ed589-140">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
