---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: d91f6ff24f8f2c051ed23565983c2bc6a2c12b55
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261423"
---
# <a name="cart-module"></a><span data-ttu-id="cb137-103">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="cb137-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cb137-104">In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb137-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cb137-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cb137-105">Overview</span></span>

<span data-ttu-id="cb137-106">Un modulo Carrello mostra gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout.</span><span class="sxs-lookup"><span data-stu-id="cb137-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="cb137-107">Il modulo mostra anche un riepilogo dell'ordine e consente al cliente di applicare o rimuovere codici promozionali.</span><span class="sxs-lookup"><span data-stu-id="cb137-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="cb137-108">Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest.</span><span class="sxs-lookup"><span data-stu-id="cb137-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="cb137-109">Supporta inoltre il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="cb137-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="cb137-110">È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.</span><span class="sxs-lookup"><span data-stu-id="cb137-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="cb137-111">Il modulo Carrello visualizza i dati in base all'ID carrello, che è un cookie del browser disponibile in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="cb137-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="cb137-112">Proprietà e slot del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="cb137-112">Cart module properties and slots</span></span>

<span data-ttu-id="cb137-113">Il modulo Carrello ha una proprietà **Intestazione** che può essere impostata su valori come **Carrello della spesa** e **Articoli nel carrello**.</span><span class="sxs-lookup"><span data-stu-id="cb137-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="cb137-114">Moduli che è possibile utilizzare in un modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="cb137-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="cb137-115">**Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="cb137-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="cb137-116">I messaggi sono gestiti dal sistema di gestione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="cb137-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="cb137-117">È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="cb137-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="cb137-118">**Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="cb137-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="cb137-119">Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="cb137-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="cb137-120">Per ulteriori informazioni su questo modulo, vedere [Modulo Selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="cb137-120">For more information on this module, see [Store selector module](store-selector.md).</span></span>


## <a name="module-properties"></a><span data-ttu-id="cb137-121">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="cb137-121">Module properties</span></span>

<span data-ttu-id="cb137-122">I moduli Carrello hanno le seguenti impostazioni che è possibile configurare in **Impostazioni sito \> Estensioni**:</span><span class="sxs-lookup"><span data-stu-id="cb137-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="cb137-123">**Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello.</span><span class="sxs-lookup"><span data-stu-id="cb137-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="cb137-124">Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="cb137-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="cb137-125">**Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb137-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="cb137-126">La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="cb137-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="cb137-127">Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="cb137-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span> <span data-ttu-id="cb137-128">Per informazioni su come configurare le impostazioni di inventario nel back office, vedere [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="cb137-128">For information on how to configure inventory settings in back office, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>
- <span data-ttu-id="cb137-129">**Buffer scorte** - Questa proprietà viene utilizzata per specificare un numero di buffer per le scorte.</span><span class="sxs-lookup"><span data-stu-id="cb137-129">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="cb137-130">Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse.</span><span class="sxs-lookup"><span data-stu-id="cb137-130">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="cb137-131">Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb137-131">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="cb137-132">Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.</span><span class="sxs-lookup"><span data-stu-id="cb137-132">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="cb137-133">**Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="cb137-133">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="cb137-134">Il ciclo di lavorazione può essere configurato a livello di sito, consentendo ai rivenditori al dettaglio di riportare il cliente sulla home page o su qualsiasi altra pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="cb137-134">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="cb137-135">Interazione con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="cb137-135">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="cb137-136">Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="cb137-136">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="cb137-137">L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="cb137-137">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="cb137-138">Aggiungere un modulo Carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="cb137-138">Add a cart module to a page</span></span>

<span data-ttu-id="cb137-139">Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="cb137-139">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="cb137-140">Creare un frammento denominato **Frammento carrello** e aggiungere un modulo Carrello al nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="cb137-140">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="cb137-141">Aggiungere un'intestazione al modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="cb137-141">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="cb137-142">Aggiungere un modulo Selettore punto vendita al modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="cb137-142">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="cb137-143">Salvare il frammento, finalizzare la modifica e quindi pubblicare il frammento.</span><span class="sxs-lookup"><span data-stu-id="cb137-143">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="cb137-144">Creare un modello denominato **Modello carrello** e aggiungere il frammento carrello appena creato.</span><span class="sxs-lookup"><span data-stu-id="cb137-144">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="cb137-145">Salvare il modello, finalizzare la modifica e quindi pubblicare il modello.</span><span class="sxs-lookup"><span data-stu-id="cb137-145">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="cb137-146">Creare una pagina che utilizza il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="cb137-146">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="cb137-147">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="cb137-147">Save and preview the page.</span></span>
1. <span data-ttu-id="cb137-148">Finalizzare la modifica e pubblicare la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb137-148">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb137-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cb137-149">Additional resources</span></span>

[<span data-ttu-id="cb137-150">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="cb137-150">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="cb137-151">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="cb137-151">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="cb137-152">Memorizzare il modulo di selezione</span><span class="sxs-lookup"><span data-stu-id="cb137-152">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="cb137-153">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="cb137-153">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="cb137-154">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="cb137-154">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="cb137-155">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="cb137-155">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="cb137-156">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="cb137-156">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="cb137-157">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="cb137-157">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="cb137-158">Modulo piè di pagina</span><span class="sxs-lookup"><span data-stu-id="cb137-158">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="cb137-159">Calcolare la disponibilità scorte per i canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="cb137-159">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
