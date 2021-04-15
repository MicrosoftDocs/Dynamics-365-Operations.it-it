---
title: Aggiungere un messaggio di benvenuto
description: In questo argomento viene descritto come aggiungere un messaggio di benvenuto al sito Web di Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797385"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="12b98-103">Aggiungere un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="12b98-103">Add a welcome message</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="12b98-104">In questo argomento viene descritto come aggiungere un messaggio di benvenuto al sito Web di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="12b98-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

<span data-ttu-id="12b98-105">Un messaggio di benvenuto nel sito Web di e-Commerce può informare i visitatori sulle vendite in corso, gli aggiornamenti del sito o la disponibilità delle collezioni stagionali.</span><span class="sxs-lookup"><span data-stu-id="12b98-105">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="12b98-106">Il messaggio di benvenuto viene impostato mediante il modulo Avviso.</span><span class="sxs-lookup"><span data-stu-id="12b98-106">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="12b98-107">Il modulo Avviso non deve essere aggiunto allo slot **Messaggi informativi/di errore** del frammento intestazione.</span><span class="sxs-lookup"><span data-stu-id="12b98-107">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="12b98-108">Il modulo Avviso consente di specificare il testo visualizzato, il colore del testo e l'allineamento.</span><span class="sxs-lookup"><span data-stu-id="12b98-108">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="12b98-109">Consente inoltre di specificare se i visitatori del sito possono chiudere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="12b98-109">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="12b98-110">Quando un messaggio di benvenuto viene aggiunto a un frammento intestazione condiviso, viene visualizzato in ogni pagina che utilizza il modello in cui è utilizzato il frammento intestazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="12b98-110">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="12b98-111">Per aggiungere un messaggio di benvenuto al sito, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="12b98-111">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="12b98-112">In Creazione di siti Web di Commerce, accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="12b98-112">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="12b98-113">Selezionare **Frammenti**.</span><span class="sxs-lookup"><span data-stu-id="12b98-113">Select **Fragments**.</span></span>
1. <span data-ttu-id="12b98-114">Selezionare il frammento intestazione a cui aggiungere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="12b98-114">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="12b98-115">Nell'albero, espandere **Messaggi informativi/di errore**.</span><span class="sxs-lookup"><span data-stu-id="12b98-115">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="12b98-116">Selezionare il modulo Avviso e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="12b98-116">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="12b98-117">Se un modulo Avviso non esiste, selezionare prima il pulsante con i puntini di sospensione (**...**) accanto a **Messaggi informativi/di errore** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12b98-117">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="12b98-118">Nel riquadro delle proprietà a destra, nella scheda **Dati** selezionare **Aggiungi origine dati** e quindi **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="12b98-118">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="12b98-119">Nel campo **Inserisci testo**, immettere il testo del messaggio di benvenuto.</span><span class="sxs-lookup"><span data-stu-id="12b98-119">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="12b98-120">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento di intestazione, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="12b98-120">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="12b98-121">Il messaggio di benvenuto viene visualizzato nella parte superiore di ogni pagina del sito che utilizza il frammento intestazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="12b98-121">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="12b98-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="12b98-122">Additional resources</span></span>

[<span data-ttu-id="12b98-123">Aggiungere un logo</span><span class="sxs-lookup"><span data-stu-id="12b98-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="12b98-124">Selezionare un tema per il sito</span><span class="sxs-lookup"><span data-stu-id="12b98-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="12b98-125">Utilizzare i file di sostituzione CSS</span><span class="sxs-lookup"><span data-stu-id="12b98-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="12b98-126">Aggiungere una favicon</span><span class="sxs-lookup"><span data-stu-id="12b98-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="12b98-127">Aggiungere informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="12b98-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="12b98-128">Aggiungere lingue al sito</span><span class="sxs-lookup"><span data-stu-id="12b98-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="12b98-129">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="12b98-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
