---
title: Applicare le impostazioni delle unità di misura
description: In questo argomento vengono descritte le impostazioni relative alle unità di misura e il modo in cui applicarle in Microsoft Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
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
ms.openlocfilehash: d1fba966434b80c9b64c1f4d9b6b87993d59c0bf
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022376"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="25914-103">Applicare le impostazioni delle unità di misura</span><span class="sxs-lookup"><span data-stu-id="25914-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="25914-104">In questo argomento vengono descritte le impostazioni relative alle unità di misura e il modo in cui applicarle in Microsoft Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="25914-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="25914-105">Un prodotto può essere venduto in unità diverse, ad esempio "pezzo", "coppia" e "dozzina".</span><span class="sxs-lookup"><span data-stu-id="25914-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="25914-106">In Commerce Headquarters è possibile definire l'unità di misura di vendita per un prodotto e visualizzarla su un sito e-commerce.</span><span class="sxs-lookup"><span data-stu-id="25914-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="25914-107">Ad esempio, se un rivenditore vende un prodotto sia individualmente che in dozzine, le unità di misura disponibili possono essere visualizzate insieme ad altre informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="25914-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="25914-108">Nell'esempio nella figura seguente, un'unità di misura di vendita al dettaglio di **pz** (pezzo) è stata configurata per un prodotto in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="25914-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Esempio di un prodotto configurato con un'unità di misura in Commerce Headquarters](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="25914-110">Il supporto per l'applicazione e la visualizzazione dell'unità di misura è disponibile a partire dalla versione Commerce 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="25914-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="25914-111">Impostazioni delle unità di misura</span><span class="sxs-lookup"><span data-stu-id="25914-111">Unit of measure settings</span></span>

<span data-ttu-id="25914-112">Le impostazioni di visualizzazione delle unità di misura sono definite in Creazione di siti di Commerce, in **Impostazioni sito \> Estensioni \> Visualizza unità di misura per i prodotti**.</span><span class="sxs-lookup"><span data-stu-id="25914-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="25914-113">Sono disponibili tre impostazioni supportate:</span><span class="sxs-lookup"><span data-stu-id="25914-113">There are three supported settings:</span></span>

- <span data-ttu-id="25914-114">**Non visualizzare** - Quando questa impostazione è selezionata, il sito di e-commerce non mostrerà l'unità di misura del prodotto.</span><span class="sxs-lookup"><span data-stu-id="25914-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="25914-115">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="25914-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="25914-116">**Visualizza nell'esperienza di acquisto del prodotto** - Quando questa impostazione è selezionata, l'unità di misura viene visualizzata nelle pagine dei dettagli del prodotto, del carrello, del checkout, della cronologia degli ordini e dei dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="25914-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="25914-117">**Visualizzazione nell'esperienza di ricerca e acquisto del prodotto** - Quando questa impostazione è selezionata, l'unità di misura viene mostrata nelle pagine dell'esperienza di acquisto del prodotto e anche durante l'esperienza di ricerca del prodotto.</span><span class="sxs-lookup"><span data-stu-id="25914-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="25914-118">Come parte di questo comportamento, le unità di misura vengono mostrate nei risultati della ricerca e nei moduli di raccolta dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="25914-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25914-119">Le impostazioni di visualizzazione delle unità di misura sono disponibili a partire dalla versione Commerce 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="25914-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="25914-120">Se stai aggiornando da una versione precedente di Commerce, devi aggiornare manualmente il file appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="25914-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="25914-121">Per istruzioni, vedi [SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="25914-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="25914-122">Moduli che utilizzano le impostazioni delle unità di misura</span><span class="sxs-lookup"><span data-stu-id="25914-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="25914-123">I moduli che utilizzano le impostazioni delle unità di misura includono la casella di acquisto, la lista dei desideri, il carrello, l'icona del carrello, il contenitore dei risultati di ricerca, la raccolta di prodotti, il checkout e i dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="25914-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="25914-124">Nell'esempio nella figura seguente, una pagina dei dettagli del prodotto (PDP) mostra l'unità di misura (**pz**) per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="25914-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Esempio di un PDP che mostra l'unità di misura](./media/Productunit-PDP.png)

<span data-ttu-id="25914-126">Nell'esempio nella figura seguente, un modulo di raccolta di prodotti mostra l'unità di misura (**pz**) per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="25914-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Esempio di un modulo di raccolta prootti che mostra l'unità di misura](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="25914-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="25914-128">Additional resources</span></span>

[<span data-ttu-id="25914-129">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="25914-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="25914-130">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="25914-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="25914-131">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="25914-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="25914-132">Moduli e pagine gestione conti</span><span class="sxs-lookup"><span data-stu-id="25914-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="25914-133">SDK e aggiornamenti della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="25914-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
