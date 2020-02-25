---
title: Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx
description: In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001134"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="e73d9-103">Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="e73d9-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e73d9-104">In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e73d9-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e73d9-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e73d9-105">Overview</span></span>

<span data-ttu-id="e73d9-106">Se una richiesta non ha esito positivo, il server genera risposte per errori di codice stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="e73d9-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="e73d9-107">Il codice stato 404 viene acquisito e restituito se una pagina non è presente e il codice stato 500 viene acquisito e restituito in caso di errore nel server.</span><span class="sxs-lookup"><span data-stu-id="e73d9-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="e73d9-108">In Dynamics 365 Commerce, gli utenti dell'applicazione possono creare pagine di risposte per errori di codice stato che sono visibili agli utenti per tali risposte.</span><span class="sxs-lookup"><span data-stu-id="e73d9-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="e73d9-109">Creare una pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="e73d9-109">Build a status code error response page</span></span>

<span data-ttu-id="e73d9-110">Per iniziare a creare una pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e73d9-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e73d9-111">Nel Web browser preferito, accedere a Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e73d9-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="e73d9-112">Selezionare il sito per il quale si desidera creare una pagina di risposte per errori di codice stato 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="e73d9-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="e73d9-113">Creare il modello</span><span class="sxs-lookup"><span data-stu-id="e73d9-113">Build the template</span></span>

<span data-ttu-id="e73d9-114">Per creare il modello per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e73d9-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e73d9-115">Andare a **Modelli \> Nuovo modello**.</span><span class="sxs-lookup"><span data-stu-id="e73d9-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="e73d9-116">Assegnare un nome al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="e73d9-116">Name the new template.</span></span>
1. <span data-ttu-id="e73d9-117">Creare il modello in base alla struttura che la pagina di risposte per errori di codice stato deve avere.</span><span class="sxs-lookup"><span data-stu-id="e73d9-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="e73d9-118">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="e73d9-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="e73d9-119">Creare la pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="e73d9-119">Build the status code error response page</span></span>

<span data-ttu-id="e73d9-120">Per creare la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e73d9-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e73d9-121">Andare a **Pagine \> Nuova pagina**.</span><span class="sxs-lookup"><span data-stu-id="e73d9-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="e73d9-122">Assegnare un nome alla pagina di risposte per errori di codice stato, ma **non** impostare il campo **URL**.</span><span class="sxs-lookup"><span data-stu-id="e73d9-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="e73d9-123">Creare la pagina.</span><span class="sxs-lookup"><span data-stu-id="e73d9-123">Build the page.</span></span>
1. <span data-ttu-id="e73d9-124">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="e73d9-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="e73d9-125">È possibile creare pagine di risposte per errori di codice stato 4xx e 5xx.</span><span class="sxs-lookup"><span data-stu-id="e73d9-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="e73d9-126">In alternativa, è possibile utilizzare la stessa pagina di risposte per errori di codice stato per entrambe le categorie di errore.</span><span class="sxs-lookup"><span data-stu-id="e73d9-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="e73d9-127">Impostare un reindirizzamento per la pagina di risposte per errori di codice stato</span><span class="sxs-lookup"><span data-stu-id="e73d9-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="e73d9-128">Per impostare un reindirizzamento per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e73d9-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e73d9-129">Andare a **URL \> Nuovo \> Nuovo alias** e selezionare la pagina di risposte per errori di codice stato creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e73d9-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="e73d9-130">Nel campo **Alias**, immettere **default-4xx** o **default-5xx**, a seconda della pagina di risposte di errore di codice stato per la quale si sta impostando un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e73d9-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="e73d9-131">Questi alias devono essere pubblicati.</span><span class="sxs-lookup"><span data-stu-id="e73d9-131">These aliases must be published.</span></span> <span data-ttu-id="e73d9-132">In caso contrario, il reindirizzamento non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e73d9-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="e73d9-133">Selezionare **OK** per eseguire il commit del collegamento.</span><span class="sxs-lookup"><span data-stu-id="e73d9-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="e73d9-134">Se si utilizza una singola pagina di risposte per errori di codice stato per entrambe le categorie di errore, ripetere questa procedura per collegare un alias per l'altra categoria di errore alla stessa pagina.</span><span class="sxs-lookup"><span data-stu-id="e73d9-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e73d9-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e73d9-135">Additional resources</span></span>

[<span data-ttu-id="e73d9-136">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="e73d9-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="e73d9-137">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="e73d9-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="e73d9-138">Creare un URL di pagina</span><span class="sxs-lookup"><span data-stu-id="e73d9-138">Create a page URL</span></span>](create-page-url.md)
