---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025438"
---
# <a name="cart-module"></a><span data-ttu-id="e68d9-103">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="e68d9-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e68d9-104">In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e68d9-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e68d9-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e68d9-105">Overview</span></span>

<span data-ttu-id="e68d9-106">Un modulo Carrello viene utilizzato per mostrare gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout.</span><span class="sxs-lookup"><span data-stu-id="e68d9-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="e68d9-107">Ad esempio, include tutti gli articoli aggiunti al carrello e un riepilogo dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="e68d9-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="e68d9-108">Inoltre, consente al cliente di applicare o rimuovere codici promozionali.</span><span class="sxs-lookup"><span data-stu-id="e68d9-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="e68d9-109">Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest.</span><span class="sxs-lookup"><span data-stu-id="e68d9-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="e68d9-110">Supporta inoltre il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="e68d9-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="e68d9-111">È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.</span><span class="sxs-lookup"><span data-stu-id="e68d9-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="e68d9-112">Il modulo Carrello esegue il rendering dei dati in base all'ID carrello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="e68d9-113">L'ID carrello è un cookie del browser disponibile in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="e68d9-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="e68d9-114">Proprietà e slot del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="e68d9-114">Cart module properties and slots</span></span>

<span data-ttu-id="e68d9-115">Il modulo Carrello ha una proprietà **Intestazione** che può essere impostata su valori come **Carrello della spesa** e **Articoli nel carrello**.</span><span class="sxs-lookup"><span data-stu-id="e68d9-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="e68d9-116">Moduli che è possibile utilizzare in un modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="e68d9-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="e68d9-117">**Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="e68d9-118">I messaggi sono gestiti dal sistema di gestione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="e68d9-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="e68d9-119">È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="e68d9-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="e68d9-120">**Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="e68d9-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="e68d9-121">Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="e68d9-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="e68d9-122">Il modulo Selettore punto vendita è integrato nell'API di geocodifica di Bing Maps per convertire l'ubicazione in una latitudine e una longitudine.</span><span class="sxs-lookup"><span data-stu-id="e68d9-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="e68d9-123">È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di vendita al dettaglio in Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="e68d9-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="e68d9-124">Questo modulo supporta due proprietà, **Raggio di ricerca** e **Collegamento Condizioni d'utilizzo**.</span><span class="sxs-lookup"><span data-stu-id="e68d9-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="e68d9-125">La proprietà **Raggio di ricerca** definisce il raggio di ricerca dei punti vendita in miglia.</span><span class="sxs-lookup"><span data-stu-id="e68d9-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="e68d9-126">Se non viene specificato alcun valore, viene utilizzato il raggio di ricerca predefinito, ovvero 50 miglia.</span><span class="sxs-lookup"><span data-stu-id="e68d9-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="e68d9-127">Se si utilizzano Bings Maps o qualsiasi altro servizio esterno, il **Collegamento Condizioni d'utilizzo** può essere utilizzato per fornire un collegamento alle condizioni d'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e68d9-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="e68d9-128">Un collegamento alle condizioni d'utilizzo è necessario per il servizio Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="e68d9-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="e68d9-129">Impostazioni del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="e68d9-129">Cart module settings</span></span>

<span data-ttu-id="e68d9-130">I moduli Carrello hanno le seguenti impostazioni che è possibile configurare in **Impostazioni sito \> Estensioni**:</span><span class="sxs-lookup"><span data-stu-id="e68d9-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="e68d9-131">**Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="e68d9-132">Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="e68d9-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="e68d9-133">**Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e68d9-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="e68d9-134">La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="e68d9-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="e68d9-135">Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="e68d9-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="e68d9-136">**Buffer scorte** - Questa proprietà viene utilizzata per specificare un numero di buffer per le scorte.</span><span class="sxs-lookup"><span data-stu-id="e68d9-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="e68d9-137">Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse.</span><span class="sxs-lookup"><span data-stu-id="e68d9-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="e68d9-138">Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile.</span><span class="sxs-lookup"><span data-stu-id="e68d9-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="e68d9-139">Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.</span><span class="sxs-lookup"><span data-stu-id="e68d9-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="e68d9-140">**Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="e68d9-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="e68d9-141">Questa route può essere configurata a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="e68d9-141">This route can be configured at the site level.</span></span> <span data-ttu-id="e68d9-142">Questa configurazione consente ai rivenditori di riportare il cliente alla home page o qualsiasi altra pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="e68d9-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="e68d9-143">Interazione con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="e68d9-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="e68d9-144">Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="e68d9-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="e68d9-145">L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="e68d9-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="e68d9-146">Aggiungere un modulo Carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="e68d9-146">Add a cart module to a page</span></span>

<span data-ttu-id="e68d9-147">Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e68d9-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e68d9-148">Creare un frammento denominato **Frammento carrello** e aggiungervi un modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="e68d9-149">Aggiungere un'intestazione al modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="e68d9-150">Aggiungere un modulo Selettore punto vendita al modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="e68d9-151">Salvare il frammento, finalizzare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="e68d9-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="e68d9-152">Creare un modello denominato **Modello carrello** e aggiungervi il frammento carrello appena creato.</span><span class="sxs-lookup"><span data-stu-id="e68d9-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="e68d9-153">Salvare il modello, finalizzare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="e68d9-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="e68d9-154">Creare una pagina che utilizza il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="e68d9-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="e68d9-155">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="e68d9-155">Save and preview the page.</span></span>
1. <span data-ttu-id="e68d9-156">Completare la modifica della pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="e68d9-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e68d9-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e68d9-157">Additional resources</span></span>

[<span data-ttu-id="e68d9-158">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="e68d9-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e68d9-159">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="e68d9-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="e68d9-160">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="e68d9-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="e68d9-161">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="e68d9-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e68d9-162">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="e68d9-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e68d9-163">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="e68d9-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="e68d9-164">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="e68d9-164">Footer module</span></span>](author-footer-module.md)
