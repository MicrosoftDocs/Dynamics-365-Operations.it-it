---
title: Aggiungere informazioni sul copyright
description: In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2ea04854636fdd0c2b3223bb19d5f06a19836151
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206369"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="1ccb7-103">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="1ccb7-103">Add a copyright notice</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1ccb7-104">In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ccb7-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ccb7-105">Prerequisites</span></span>

<span data-ttu-id="1ccb7-106">Prima di aggiungere informazioni sul copyright al sito, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1ccb7-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="1ccb7-107">Un modello che include un frammento piè di pagina condiviso.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="1ccb7-108">Una pagina che utilizza quel modello.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="1ccb7-109">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="1ccb7-109">Add a copyright notice</span></span>

<span data-ttu-id="1ccb7-110">Per aggiungere informazioni sul copyright nella parte inferiore di ogni pagina che utilizza un modello specifico, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="1ccb7-111">Andare a **Frammenti** quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-111">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="1ccb7-112">Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Piè di pagina** e denominare il frammento.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-112">In the **New fragment** dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="1ccb7-113">Ad esempio, immettere **Piè di pagina-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="1ccb7-114">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-114">Select **OK**.</span></span>
1. <span data-ttu-id="1ccb7-115">Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione (**...**) accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1ccb7-116">Nella finestra di dialogo, selezionare **Categoria piè di pagina** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="1ccb7-117">Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1ccb7-118">Nella finestra di dialogo, selezionare **Blocco di testo** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-118">In the dialog box, select **Text block**, and then select **OK**.</span></span>
1. <span data-ttu-id="1ccb7-119">Nel pannello di navigazione, selezionare **Blocco di testo**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-119">In the navigation pane, select **Text block**.</span></span>
1. <span data-ttu-id="1ccb7-120">Nel riquadro delle proprietà a destra, nel campo **Paragrafo**, aggiungere le informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="1ccb7-121">Ad esempio, immettere **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="1ccb7-122">Selezionare **Salva**, **Fine modifica** e quindi **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-122">Select **Save**, select **Finish editing**, and then select **Publish**.</span></span>
1. <span data-ttu-id="1ccb7-123">Andare a **Modelli**, selezionare il modello e quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-123">Go to **Templates**, select the template, and then select **Edit**.</span></span>
1. <span data-ttu-id="1ccb7-124">Sotto **Struttura pagina** espandere **Corpo** e quindi **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="1ccb7-125">Selezionare il pulsante con i puntini di sospensione accanto a **Slot piè di pagina** e quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="1ccb7-126">Selezionare il frammento creato in precedenza e quindi **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="1ccb7-127">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-127">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="1ccb7-128">Il piè di pagina contenente le informazioni sul copyright viene automaticamente visualizzato nella parte inferiore di tutte le pagine che utilizzano il modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ccb7-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ccb7-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1ccb7-129">Additional resources</span></span>

[<span data-ttu-id="1ccb7-130">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="1ccb7-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="1ccb7-131">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="1ccb7-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="1ccb7-132">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="1ccb7-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="1ccb7-133">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="1ccb7-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="1ccb7-134">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="1ccb7-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="1ccb7-135">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="1ccb7-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="1ccb7-136">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="1ccb7-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]