---
title: Aggiungere informazioni sul copyright
description: In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.
author: psimolin
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 39135a2eca25336097ee9eddf06dc6709c102571
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696947"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="623fe-103">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="623fe-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="623fe-104">In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="623fe-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="623fe-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="623fe-105">Prerequisites</span></span>

<span data-ttu-id="623fe-106">Prima di aggiungere informazioni sul copyright al sito, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="623fe-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="623fe-107">Un modello che include un frammento piè di pagina condiviso.</span><span class="sxs-lookup"><span data-stu-id="623fe-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="623fe-108">Una pagina che utilizza quel modello.</span><span class="sxs-lookup"><span data-stu-id="623fe-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="623fe-109">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="623fe-109">Add a copyright notice</span></span>

<span data-ttu-id="623fe-110">Per aggiungere informazioni sul copyright nella parte inferiore di ogni pagina che utilizza un modello specifico, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="623fe-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="623fe-111">Andare a **Frammenti** e quindi selezionare **Nuovo frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="623fe-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="623fe-112">Nella finestra di dialogo, selezionare il modulo **Piè di pagina** e assegnare un nome al frammento.</span><span class="sxs-lookup"><span data-stu-id="623fe-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="623fe-113">Ad esempio, immettere **Piè di pagina-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="623fe-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="623fe-114">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="623fe-114">Select **OK**.</span></span>
1. <span data-ttu-id="623fe-115">Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione (**...**) accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="623fe-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="623fe-116">Nella finestra di dialogo, selezionare **Categoria piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="623fe-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="623fe-117">Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="623fe-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="623fe-118">Nella finestra di dialogo, selezionare **Elemento blocco ricco di contenuti** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="623fe-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="623fe-119">Nel pannello di navigazione, selezionare **Elemento blocco ricco di contenuti**.</span><span class="sxs-lookup"><span data-stu-id="623fe-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="623fe-120">Nel riquadro delle proprietà a destra, nel campo **Paragrafo**, aggiungere le informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="623fe-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="623fe-121">Ad esempio, immettere **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="623fe-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="623fe-122">Selezionare **Salva**, **Archivia** e quindi **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="623fe-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="623fe-123">In **Modelli**, selezionare il modello e quindi **Estrai**.</span><span class="sxs-lookup"><span data-stu-id="623fe-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="623fe-124">Sotto **Struttura pagina** espandere **Corpo** e quindi **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="623fe-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="623fe-125">Selezionare il pulsante con i puntini di sospensione accanto a **Slot piè di pagina** e quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="623fe-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="623fe-126">Selezionare il frammento creato in precedenza e quindi **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="623fe-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="623fe-127">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="623fe-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="623fe-128">Il piè di pagina contenente le informazioni sul copyright viene automaticamente visualizzato nella parte inferiore di tutte le pagine che utilizzano il modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="623fe-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="623fe-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="623fe-129">Additional resources</span></span>

[<span data-ttu-id="623fe-130">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="623fe-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="623fe-131">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="623fe-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="623fe-132">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="623fe-132">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="623fe-133">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="623fe-133">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="623fe-134">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="623fe-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="623fe-135">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="623fe-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

