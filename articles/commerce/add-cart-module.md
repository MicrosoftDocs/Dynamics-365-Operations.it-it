---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154019"
---
# <a name="cart-module"></a><span data-ttu-id="9dcaf-103">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="9dcaf-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9dcaf-104">In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9dcaf-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9dcaf-105">Overview</span></span>

<span data-ttu-id="9dcaf-106">Un modulo Carrello mostra gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="9dcaf-107">Il modulo mostra anche un riepilogo dell'ordine e consente al cliente di applicare o rimuovere codici promozionali.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="9dcaf-108">Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="9dcaf-109">Supporta inoltre il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="9dcaf-110">È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="9dcaf-111">Il modulo Carrello visualizza i dati in base all'ID carrello, che è un cookie del browser disponibile in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="9dcaf-112">Proprietà e slot del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="9dcaf-112">Cart module properties and slots</span></span>

<span data-ttu-id="9dcaf-113">Il modulo Carrello ha una proprietà **Intestazione** che può essere impostata su valori come **Carrello della spesa** e **Articoli nel carrello**.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="9dcaf-114">Moduli che è possibile utilizzare in un modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="9dcaf-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="9dcaf-115">**Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="9dcaf-116">I messaggi sono gestiti dal sistema di gestione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="9dcaf-117">È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="9dcaf-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="9dcaf-118">**Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="9dcaf-119">Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="9dcaf-120">Per ulteriori informazioni su questo modulo, vedere [Modulo Selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="9dcaf-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="9dcaf-121">Impostazioni del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="9dcaf-121">Cart module settings</span></span>

<span data-ttu-id="9dcaf-122">I moduli Carrello hanno le seguenti impostazioni che è possibile configurare in **Impostazioni sito \> Estensioni**:</span><span class="sxs-lookup"><span data-stu-id="9dcaf-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="9dcaf-123">**Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="9dcaf-124">Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="9dcaf-125">**Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="9dcaf-126">La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="9dcaf-127">Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="9dcaf-128">**Buffer scorte** - Questa proprietà viene utilizzata per specificare un numero di buffer per le scorte.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="9dcaf-129">Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="9dcaf-130">Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="9dcaf-131">Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="9dcaf-132">**Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="9dcaf-133">Il ciclo di lavorazione può essere configurato a livello di sito, consentendo ai rivenditori al dettaglio di riportare il cliente sulla home page o su qualsiasi altra pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="9dcaf-134">Interazione con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="9dcaf-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="9dcaf-135">Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="9dcaf-136">L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="9dcaf-137">Aggiungere un modulo Carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="9dcaf-137">Add a cart module to a page</span></span>

<span data-ttu-id="9dcaf-138">Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="9dcaf-139">Creare un frammento denominato **Frammento carrello** e aggiungere un modulo Carrello al nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="9dcaf-140">Aggiungere un'intestazione al modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="9dcaf-141">Aggiungere un modulo Selettore punto vendita al modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="9dcaf-142">Salvare il frammento, finalizzare la modifica e quindi pubblicare il frammento.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="9dcaf-143">Creare un modello denominato **Modello carrello** e aggiungere il frammento carrello appena creato.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="9dcaf-144">Salvare il modello, finalizzare la modifica e quindi pubblicare il modello.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="9dcaf-145">Creare una pagina che utilizza il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="9dcaf-146">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-146">Save and preview the page.</span></span>
1. <span data-ttu-id="9dcaf-147">Finalizzare la modifica e pubblicare la pagina.</span><span class="sxs-lookup"><span data-stu-id="9dcaf-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9dcaf-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9dcaf-148">Additional resources</span></span>

[<span data-ttu-id="9dcaf-149">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="9dcaf-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9dcaf-150">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="9dcaf-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="9dcaf-151">Modulo Selettore punto vendita</span><span class="sxs-lookup"><span data-stu-id="9dcaf-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="9dcaf-152">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="9dcaf-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="9dcaf-153">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="9dcaf-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="9dcaf-154">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="9dcaf-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="9dcaf-155">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="9dcaf-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="9dcaf-156">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="9dcaf-156">Footer module</span></span>](author-footer-module.md)
