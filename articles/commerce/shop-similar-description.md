---
title: Abilita gli elementi consigliati "acquista descrizioni simili"
description: Questo argomento descrive come abilitare i consigli sui prodotti "acquista descrizioni simili" in Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b6b397b1f21e3dfcdb4a2b7fe67ddb541d090a97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234391"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="a0247-103">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="a0247-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0247-104">Questo argomento descrive come abilitare i consigli sui prodotti "acquista descrizioni simili" in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a0247-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a0247-105">La funzionalità relativa ai consigli "acquista descrizioni simili" in Dynamics 365 Commerce utilizza l'intelligenza artificiale e l'apprendimento automatico (IA-ML) per fornire ai clienti consigli per prodotti le cui descrizioni sono simili a ciò che ha cercato il cliente.</span><span class="sxs-lookup"><span data-stu-id="a0247-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="a0247-106">Rendendo disponibili i consigli "acquista descrizioni simili" per tutti i canali di vendita al dettaglio in Commerce, i rivenditori possono aiutare i clienti a trovare facilmente ciò che desiderano.</span><span class="sxs-lookup"><span data-stu-id="a0247-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="a0247-107">La funzionalità per i consigli "acquista descrizioni simili" utilizza il nome e la descrizione del prodotto di prodotti iniziali per trovare prodotti simili consigliati in un catalogo di prodotti di un rivenditore.</span><span class="sxs-lookup"><span data-stu-id="a0247-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="a0247-108">I consigli "acquista descrizioni simili" sono disponibili sia nelle esperienze POS che e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a0247-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="a0247-109">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="a0247-109">Example scenarios</span></span>

<span data-ttu-id="a0247-110">I seguenti scenari di esempio mostrano i tipi di consigli che la funzionalità "Descrizione negozio simile" può fornire:</span><span class="sxs-lookup"><span data-stu-id="a0247-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="a0247-111">Un cliente visualizza un paio di occhiali cerchiati di corno in stile retrò e riceve una serie di consigli per altri occhiali con un design simile, nel contesto del settore del rivenditore.</span><span class="sxs-lookup"><span data-stu-id="a0247-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="a0247-112">Un cliente utilizza i consigli "Descrizione negozio simile" per scoprire gusti di caffè simili a un gusto che ha acquistato in precedenza dal rivenditore.</span><span class="sxs-lookup"><span data-stu-id="a0247-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="a0247-113">Configura consigli "acquista descrizioni simili"</span><span class="sxs-lookup"><span data-stu-id="a0247-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="a0247-114">I consigli relativi ai prodotti sono supportati solo per gli utenti Commerce che hanno eseguito la migrazione del loro archivio ad Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="a0247-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a0247-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a0247-115">Prerequisites</span></span>

<span data-ttu-id="a0247-116">Prima di mostrare ai clienti i consigli "acquista descrizioni simili", è necessario completare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="a0247-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="a0247-117">[Abilitare suggerimenti sul prodotto](enable-product-recommendations.md) in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="a0247-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="a0247-118">Verificare che il server multimediale supporti le chiamate HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a0247-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="a0247-119">Abilita la funzionalità dei consigli "acquista descrizioni simili"</span><span class="sxs-lookup"><span data-stu-id="a0247-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="a0247-120">Per abilitare la funzione dei consigli "acquista descrizioni simili" in Commerce Headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a0247-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a0247-121">Nell'area di lavoro **Gestione funzionalità**, nell'elenco delle funzionalità disponibili, cercare e selezionare **Acquista descrizioni simili**.</span><span class="sxs-lookup"><span data-stu-id="a0247-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="a0247-122">Nel riquadro di destra, seleziona **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="a0247-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="a0247-123">Quando si attiva la funzionalità, il sistema inizia a generare elenchi di suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="a0247-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="a0247-124">Potrebbe essere necessario fino a un giorno affinché questi elenchi siano disponibili e visibili online e nei terminali POS.</span><span class="sxs-lookup"><span data-stu-id="a0247-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="a0247-125">Se disattivi la funzione, altri tipi di consigli sui prodotti non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="a0247-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="a0247-126">Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="a0247-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="a0247-127">Aggiungi un pulsante Acquista descrizioni simili alle pagine dei dettagli del prodotto</span><span class="sxs-lookup"><span data-stu-id="a0247-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="a0247-128">Dopo aver abilitato la funzione di consigli "acquista descrizioni simili" in Commerce Headquarters, puoi aggiungere un pulsante **Acquista descrizioni simili** per la casella di acquisto nella pagina dei dettagli del prodotto (PDP).</span><span class="sxs-lookup"><span data-stu-id="a0247-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="a0247-129">Un cliente che seleziona questo pulsante viene indirizzato a una pagina dedicata **Acquista descrizioni simili** che restituisce prodotti visivamente simili.</span><span class="sxs-lookup"><span data-stu-id="a0247-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="a0247-130">Il cliente può quindi utilizzare i selettori per filtrare ulteriormente i prodotti.</span><span class="sxs-lookup"><span data-stu-id="a0247-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="a0247-131">Per aggiungere un pulsante **Descrizione prodotti simili** alle pagine dei dettagli dei prodotti utilizzando la creazione di siti Commerce, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a0247-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0247-132">Aprire una pagina di creazione di siti Web che contiene un modulo Casella acquisti.</span><span class="sxs-lookup"><span data-stu-id="a0247-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="a0247-133">Selezionare il modulo Casella acquisti nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="a0247-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="a0247-134">Nel riquadro di navigazione a destra, seleziona la casella di controllo **Abilita collegamento acquista descrizione simili**.</span><span class="sxs-lookup"><span data-stu-id="a0247-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="a0247-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0247-135">Select **Save**.</span></span>
1. <span data-ttu-id="a0247-136">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="a0247-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="a0247-137">Dopo la pubblicazione della pagina, la pagina dei dettagli del prodotto includerà un pulsante **Acquista descrizione simili**.</span><span class="sxs-lookup"><span data-stu-id="a0247-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="a0247-138">La figura seguente mostra la casella di controllo **Abilita collegamento acquista descrizione simili** e il pulsante **Acquista descrizioni simili** in una pagina dei dettagli del prodotto di esempio in Creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="a0247-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![Casella di controllo Abilita collegamento acquista descrizione simili e il pulsante Acquista descrizioni simili in una pagina dei dettagli del prodotto in Creazione di siti](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="a0247-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a0247-140">Additional resources</span></span>

[<span data-ttu-id="a0247-141">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="a0247-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="a0247-142">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a0247-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="a0247-143">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="a0247-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="a0247-144">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="a0247-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="a0247-145">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="a0247-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="a0247-146">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="a0247-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="a0247-147">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="a0247-147">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]