---
title: Applicare le impostazioni di visualizzazione per le dimensioni del prodotto
description: Questo argomento illustra le impostazioni di visualizzazione per le dimensioni del prodotto e descrive come applicarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117231"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="d1d98-103">Applicare le impostazioni di visualizzazione per le dimensioni del prodotto</span><span class="sxs-lookup"><span data-stu-id="d1d98-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="d1d98-104">Questo argomento illustra le impostazioni di visualizzazione per le dimensioni del prodotto e descrive come applicarle in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d1d98-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d1d98-105">Dynamics 365 Commerce supporta dimensioni, stile e colore per distinguere le varianti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d1d98-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="d1d98-106">Le dimensioni vengono generalmente visualizzate come valori di testo, ad esempio "Piccolo", "Medio" e "Grande" per le dimensioni e "Nero" e "Marrone" per i colori.</span><span class="sxs-lookup"><span data-stu-id="d1d98-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="d1d98-107">Tuttavia, se un prodotto supporta molte varianti potrebbe essere difficile esplorare le varianti di prodotto, poiché sono necessarie più selezioni per visualizzare l'immagine per ciascuna variante di prodotto.</span><span class="sxs-lookup"><span data-stu-id="d1d98-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="d1d98-108">Per semplificare la ricerca delle varianti di prodotto, la versione 10.0.20 di Commerce può utilizzare immagini e codici esadecimali (esadecimali) per mostrare le dimensioni come campioni.</span><span class="sxs-lookup"><span data-stu-id="d1d98-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="d1d98-109">In Commerce Site Builder, le impostazioni di dimensione sono definite in **Impostazioni sito \> Estensioni \> Impostazioni dimensione**.</span><span class="sxs-lookup"><span data-stu-id="d1d98-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="d1d98-110">La figura seguente mostra un esempio di impostazioni delle dimensioni in Site Builder.</span><span class="sxs-lookup"><span data-stu-id="d1d98-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Esempio di impostazioni del sito in Commerce Site Builder](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="d1d98-112">Sono disponibili due impostazioni di dimensione:</span><span class="sxs-lookup"><span data-stu-id="d1d98-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="d1d98-113">**Dimensioni da visualizzare come immagine**: specifica le dimensioni da visualizzare come campioni nelle pagine del sito di e-commerce come le pagine dei dettagli del prodotto (PDP) e le pagine dell'elenco dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d1d98-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="d1d98-114">Qualsiasi combinazione di colore, dimensione e dimensioni dello stile può essere visualizzata come campione.</span><span class="sxs-lookup"><span data-stu-id="d1d98-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="d1d98-115">Se una dimensione viene selezionata per la visualizzazione come campione, il rendering del modulo Commerce cercherà una configurazione disponibile di un campione di codice esadecimale.</span><span class="sxs-lookup"><span data-stu-id="d1d98-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="d1d98-116">Se non è configurato alcun codice esadecimale, la logica di sistema cercherà una configurazione di un campione di URL immagine.</span><span class="sxs-lookup"><span data-stu-id="d1d98-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="d1d98-117">Se non è configurato né un codice esadecimale né un URL immagine, verrà visualizzato il testo.</span><span class="sxs-lookup"><span data-stu-id="d1d98-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="d1d98-118">La seguente illustrazione mostra un esempio in cui i colori vengono visualizzati come campioni su un PDP o un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="d1d98-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="d1d98-119">In questo esempio, un codice esadecimale è configurato per la dimensione del colore.</span><span class="sxs-lookup"><span data-stu-id="d1d98-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="d1d98-120">Pertanto, i campioni vengono visualizzati come colori.</span><span class="sxs-lookup"><span data-stu-id="d1d98-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="d1d98-121">Tuttavia, per la dimensione non sono configurati né un codice esadecimale né un URL immagine.</span><span class="sxs-lookup"><span data-stu-id="d1d98-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="d1d98-122">Pertanto, viene visualizzato il testo.</span><span class="sxs-lookup"><span data-stu-id="d1d98-122">Therefore, text is shown.</span></span>

    ![Esempio della dimensione del colore mostrata come campioni nella pagina dei dettagli di un prodotto e-commerce](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="d1d98-124">**Dimensioni da visualizzare nella scheda prodotto**: specifica quali dimensioni devono apparire sulle schede prodotto che vengono mostrate negli elenchi e nelle pagine degli elenchi.</span><span class="sxs-lookup"><span data-stu-id="d1d98-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="d1d98-125">Prima che una dimensione possa essere visualizzata su una scheda prodotto, questa impostazione deve essere abilitata per quella dimensione.</span><span class="sxs-lookup"><span data-stu-id="d1d98-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="d1d98-126">Anche l'impostazione **Dimensioni da visualizzare come immagine** dovrebbe essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="d1d98-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="d1d98-127">Il comportamento di selezione dei campioni sulle schede prodotto è ottimizzato per la dimensione del colore.</span><span class="sxs-lookup"><span data-stu-id="d1d98-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="d1d98-128">Per altre dimensioni, potrebbe essere necessaria un'estensione della visualizzazione per personalizzare il comportamento di selezione dei campioni.</span><span class="sxs-lookup"><span data-stu-id="d1d98-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="d1d98-129">La figura seguente mostra un esempio in cui una pagina di elenco su un sito di e-commerce contiene schede prodotto che includono campioni di colore.</span><span class="sxs-lookup"><span data-stu-id="d1d98-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Esempio della dimensione del colore mostrata come campioni nella pagina elenco e-commerce](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="d1d98-131">Per informazioni su come configurare le dimensioni del prodotto in modo che vengano visualizzate come campioni nelle pagine del sito, vedi [Configurare i valori delle dimensioni del prodotto in modo che appaiano come campioni](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="d1d98-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1d98-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d1d98-132">Additional resources</span></span>

[<span data-ttu-id="d1d98-133">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="d1d98-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d1d98-134">Modulo dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="d1d98-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="d1d98-135">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="d1d98-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d1d98-136">Configurare i valori di dimensione prodotto in modo che appaiano come campioni</span><span class="sxs-lookup"><span data-stu-id="d1d98-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
