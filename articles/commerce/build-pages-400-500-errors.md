---
title: Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx
description: In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee2f74581ded6020d075377f931c465d7c89f9e5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211107"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="198be-103">Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="198be-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="198be-104">In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="198be-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="198be-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="198be-105">Overview</span></span>

<span data-ttu-id="198be-106">Se una richiesta non ha esito positivo, il server genera risposte per errori di codice stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="198be-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="198be-107">Il codice stato 404 viene acquisito e restituito se una pagina non è presente e il codice stato 500 viene acquisito e restituito in caso di errore nel server.</span><span class="sxs-lookup"><span data-stu-id="198be-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="198be-108">In Dynamics 365 Commerce, gli utenti dell'applicazione possono creare pagine di risposte per errori di codice stato che sono visibili agli utenti per tali risposte.</span><span class="sxs-lookup"><span data-stu-id="198be-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="198be-109">Creare una pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="198be-109">Build a status code error response page</span></span>

<span data-ttu-id="198be-110">Per iniziare a creare una pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="198be-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="198be-111">Nel Web browser preferito, accedere a Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="198be-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="198be-112">Selezionare il sito per il quale si desidera creare una pagina di risposte per errori di codice stato 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="198be-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="198be-113">Creare il modello</span><span class="sxs-lookup"><span data-stu-id="198be-113">Build the template</span></span>

<span data-ttu-id="198be-114">Per creare il modello per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="198be-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="198be-115">Andare a **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="198be-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="198be-116">Selezionare **Nuovo** per creare un modello di pagina.</span><span class="sxs-lookup"><span data-stu-id="198be-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="198be-117">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per il nuovo modello e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="198be-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="198be-118">Creare il modello in base alla struttura che la pagina di risposte per errori di codice stato deve avere.</span><span class="sxs-lookup"><span data-stu-id="198be-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="198be-119">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="198be-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="198be-120">Creare la pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="198be-120">Build the status code error response page</span></span>

<span data-ttu-id="198be-121">Per creare la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="198be-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="198be-122">Andare a **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="198be-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="198be-123">Selezionare **Nuovo** per creare una pagina.</span><span class="sxs-lookup"><span data-stu-id="198be-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="198be-124">Nella finestra di dialogo **Scegli un modello**, selezionare un modello, quindi in **Nome pagina**, inserire un nome per la pagina di risposta dell'errore del codice di stato.</span><span class="sxs-lookup"><span data-stu-id="198be-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="198be-125">Lasciare vuoto il campo **URL pagina**.</span><span class="sxs-lookup"><span data-stu-id="198be-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="198be-126">Creare la pagina.</span><span class="sxs-lookup"><span data-stu-id="198be-126">Build the page.</span></span>
1. <span data-ttu-id="198be-127">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="198be-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="198be-128">È possibile creare pagine di risposte per errori di codice stato 4xx e 5xx.</span><span class="sxs-lookup"><span data-stu-id="198be-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="198be-129">In alternativa, è possibile utilizzare la stessa pagina di risposte per errori di codice stato per entrambe le categorie di errore.</span><span class="sxs-lookup"><span data-stu-id="198be-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="198be-130">Impostare un reindirizzamento per la pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="198be-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="198be-131">Per impostare un reindirizzamento per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="198be-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="198be-132">Andare a **URL \> Nuovo \> Nuovo alias** e selezionare la pagina di risposte per errori di codice stato creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="198be-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="198be-133">Nel campo **Alias**, immettere **default-4xx** o **default-5xx**, a seconda della pagina di risposte di errore di codice stato per la quale si sta impostando un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="198be-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="198be-134">Questi alias devono essere pubblicati.</span><span class="sxs-lookup"><span data-stu-id="198be-134">These aliases must be published.</span></span> <span data-ttu-id="198be-135">In caso contrario, il reindirizzamento non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="198be-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="198be-136">Selezionare **OK** per eseguire il commit del collegamento.</span><span class="sxs-lookup"><span data-stu-id="198be-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="198be-137">Se si utilizza una singola pagina di risposte per errori di codice stato per entrambe le categorie di errore, ripetere questa procedura per collegare un alias per l'altra categoria di errore alla stessa pagina.</span><span class="sxs-lookup"><span data-stu-id="198be-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="198be-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="198be-138">Additional resources</span></span>

[<span data-ttu-id="198be-139">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="198be-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="198be-140">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="198be-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="198be-141">Creare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="198be-141">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]