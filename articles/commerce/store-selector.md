---
title: Modulo Selettore punto vendita
description: In questo argomento viene descritto il modulo selettore punto vendita e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157342"
---
# <a name="store-selector-module"></a><span data-ttu-id="2da01-103">Modulo Selettore punto vendita</span><span class="sxs-lookup"><span data-stu-id="2da01-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2da01-104">In questo argomento viene descritto il modulo selettore punto vendita e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2da01-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2da01-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="2da01-105">Overview</span></span>

<span data-ttu-id="2da01-106">Un modulo selettore punto vendita viene utilizzato per lo scenario del cliente "acquisto online, ritiro in negozio" (BOPIS).</span><span class="sxs-lookup"><span data-stu-id="2da01-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="2da01-107">Visualizza un elenco di negozi in cui un prodotto è disponibile per il ritiro, nonché gli orari e l'inventario del prodotto per ciascun negozio.</span><span class="sxs-lookup"><span data-stu-id="2da01-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="2da01-108">Il modulo selettore punto vendita richiede il contesto di un prodotto e una posizione di ricerca per trovare i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="2da01-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="2da01-109">In assenza di un percorso di ricerca, viene impostato automaticamente il percorso del browser del cliente, a condizione che il cliente fornisca il consenso.</span><span class="sxs-lookup"><span data-stu-id="2da01-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="2da01-110">Il modulo ha una casella di input che consente al cliente di inserire una posizione (codice postale o città e stato) per trovare i negozi nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="2da01-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="2da01-111">Il modulo Selettore punto vendita è integrato nell'API di geocodifica di Bing Maps per convertire l'ubicazione in una latitudine e una longitudine.</span><span class="sxs-lookup"><span data-stu-id="2da01-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="2da01-112">È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di commercio in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2da01-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2da01-113">Il modulo selettore punto vendita può essere aggiunto a un modulo casella acquisti nella pagina dei dettagli del prodotto (PDP) per visualizzare i negozi in cui un prodotto è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="2da01-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="2da01-114">Può anche essere aggiunto a un modulo carrello.</span><span class="sxs-lookup"><span data-stu-id="2da01-114">It can also be added to a cart module.</span></span> <span data-ttu-id="2da01-115">Quando aggiunto a un modulo carrello, il modulo selettore punto vendita visualizza le opzioni di ritiro per ciascun articolo nel carrello.</span><span class="sxs-lookup"><span data-stu-id="2da01-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="2da01-116">Inoltre, con la codifica personalizzata questo modulo può essere aggiunto ad altre pagine o moduli tramite estensioni e personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2da01-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="2da01-117">Affinché lo scenario BOPIS funzioni, i prodotti devono essere configurati con la modalità di consegna "ritiro del cliente".</span><span class="sxs-lookup"><span data-stu-id="2da01-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="2da01-118">Altrimenti, il modulo non verrà mostrato nelle rispettive pagine.</span><span class="sxs-lookup"><span data-stu-id="2da01-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="2da01-119">Per i dettagli su come configurare la modalità di consegna, vedere [Impostare le modalità di consegna](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="2da01-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="2da01-120">L'immagine seguente mostra un esempio di un modulo selettore punto vendita utilizzato su un PDP.</span><span class="sxs-lookup"><span data-stu-id="2da01-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Esempio di un modulo selettore punto vendita](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="2da01-122">Utilizzo del modulo selettore punto vendita in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="2da01-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="2da01-123">Un modulo selettore punto vendita può essere usato come pagina dei dettagli del prodotto (PDP) per trovare i negozi nelle vicinanze in cui un prodotto è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="2da01-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="2da01-124">Un modulo selettore punto vendita può essere usato in una pagina carrello per trovare i negozi nelle vicinanze in cui un prodotto nel carrello è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="2da01-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="2da01-125">Proprietà del modulo selettore punto vendita</span><span class="sxs-lookup"><span data-stu-id="2da01-125">Store selector module properties</span></span>

| <span data-ttu-id="2da01-126">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="2da01-126">Property name</span></span>             | <span data-ttu-id="2da01-127">Valore</span><span class="sxs-lookup"><span data-stu-id="2da01-127">Value</span></span>                 | <span data-ttu-id="2da01-128">descrizione</span><span class="sxs-lookup"><span data-stu-id="2da01-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="2da01-129">Raggio di ricerca</span><span class="sxs-lookup"><span data-stu-id="2da01-129">Search radius</span></span> | <span data-ttu-id="2da01-130">Numero</span><span class="sxs-lookup"><span data-stu-id="2da01-130">Number</span></span> | <span data-ttu-id="2da01-131">Definisce il raggio di ricerca dei negozi, in miglia.</span><span class="sxs-lookup"><span data-stu-id="2da01-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="2da01-132">Se non viene specificato alcun valore, viene utilizzato il raggio di ricerca predefinito, ovvero 50 miglia.</span><span class="sxs-lookup"><span data-stu-id="2da01-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="2da01-133">Condizioni d'uso</span><span class="sxs-lookup"><span data-stu-id="2da01-133">Terms of Service</span></span> | <span data-ttu-id="2da01-134">URL</span><span class="sxs-lookup"><span data-stu-id="2da01-134">URL</span></span>    |  <span data-ttu-id="2da01-135">L'URL delle condizioni d'utilizzo è necessario per il servizio Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="2da01-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="2da01-136">Aggiungere un modulo selettore punto vendita a una pagina</span><span class="sxs-lookup"><span data-stu-id="2da01-136">Add a store selector module to a page</span></span>

<span data-ttu-id="2da01-137">Un modulo modulo selettore punto vendita ha bisogno del contesto di un prodotto, quindi può essere utilizzato solo nei moduli acquisto e carrello.</span><span class="sxs-lookup"><span data-stu-id="2da01-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="2da01-138">I moduli modulo selettore punto vendita non funzionano al di fuori di questi moduli.</span><span class="sxs-lookup"><span data-stu-id="2da01-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="2da01-139">Per informazioni su come aggiungere un modulo modulo selettore punto vendita a un modulo di acquisto, vedere [Modulo casella acquisti](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="2da01-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="2da01-140">Per informazioni su come aggiungere un modulo modulo selettore punto vendita a un modulo carrello, vedere [Modulo carrello](add-cart-module.md).</span><span class="sxs-lookup"><span data-stu-id="2da01-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2da01-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2da01-141">Additional resources</span></span>

[<span data-ttu-id="2da01-142">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="2da01-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2da01-143">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="2da01-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="2da01-144">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="2da01-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="2da01-145">Demo veloce di PDP</span><span class="sxs-lookup"><span data-stu-id="2da01-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="2da01-146">Demo veloce di carrello e check out</span><span class="sxs-lookup"><span data-stu-id="2da01-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="2da01-147">Imposta la modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="2da01-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
