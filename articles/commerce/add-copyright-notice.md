---
title: Aggiungere informazioni sul copyright
description: In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.
author: psimolin
manager: AnnBe
ms.date: 12/12/2019
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
ms.openlocfilehash: 58c2949057ef777f706d12cee2dd3341d1a3b7e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914575"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="e286d-103">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="e286d-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e286d-104">In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="e286d-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e286d-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e286d-105">Prerequisites</span></span>

<span data-ttu-id="e286d-106">Prima di aggiungere informazioni sul copyright al sito, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e286d-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="e286d-107">Un modello che include un frammento piè di pagina condiviso.</span><span class="sxs-lookup"><span data-stu-id="e286d-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="e286d-108">Una pagina che utilizza quel modello.</span><span class="sxs-lookup"><span data-stu-id="e286d-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="e286d-109">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="e286d-109">Add a copyright notice</span></span>

<span data-ttu-id="e286d-110">Per aggiungere informazioni sul copyright nella parte inferiore di ogni pagina che utilizza un modello specifico, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e286d-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="e286d-111">Andare a **Frammenti** e quindi selezionare **Nuovo frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="e286d-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="e286d-112">Nella finestra di dialogo, selezionare il modulo **Piè di pagina** e assegnare un nome al frammento.</span><span class="sxs-lookup"><span data-stu-id="e286d-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="e286d-113">Ad esempio, immettere **Piè di pagina-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="e286d-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="e286d-114">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e286d-114">Select **OK**.</span></span>
1. <span data-ttu-id="e286d-115">Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione (**...**) accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e286d-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e286d-116">Nella finestra di dialogo, selezionare **Categoria piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="e286d-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="e286d-117">Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e286d-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e286d-118">Nella finestra di dialogo, selezionare **Elemento blocco ricco di contenuti** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="e286d-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="e286d-119">Nel pannello di navigazione, selezionare **Elemento blocco ricco di contenuti**.</span><span class="sxs-lookup"><span data-stu-id="e286d-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="e286d-120">Nel riquadro delle proprietà a destra, nel campo **Paragrafo**, aggiungere le informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="e286d-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="e286d-121">Ad esempio, immettere **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="e286d-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="e286d-122">Selezionare **Salva**, **Archivia** e quindi **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="e286d-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="e286d-123">In **Modelli**, selezionare il modello e quindi **Estrai**.</span><span class="sxs-lookup"><span data-stu-id="e286d-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="e286d-124">Sotto **Struttura pagina** espandere **Corpo** e quindi **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="e286d-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="e286d-125">Selezionare il pulsante con i puntini di sospensione accanto a **Slot piè di pagina** e quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="e286d-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="e286d-126">Selezionare il frammento creato in precedenza e quindi **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="e286d-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="e286d-127">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="e286d-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="e286d-128">Il piè di pagina contenente le informazioni sul copyright viene automaticamente visualizzato nella parte inferiore di tutte le pagine che utilizzano il modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="e286d-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e286d-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e286d-129">Additional resources</span></span>

[<span data-ttu-id="e286d-130">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="e286d-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="e286d-131">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="e286d-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e286d-132">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="e286d-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e286d-133">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="e286d-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e286d-134">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="e286d-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e286d-135">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="e286d-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="e286d-136">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="e286d-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

