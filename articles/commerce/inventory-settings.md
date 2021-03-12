---
title: Applicare impostazioni relative alle scorte
description: In questo argomento vengono descritte le impostazioni relative alle scorte e il modo in cui applicarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 77a3bde12fd047e15d7730903416cdb5263a8cd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972811"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="1bc7a-103">Applicare impostazioni relative alle scorte</span><span class="sxs-lookup"><span data-stu-id="1bc7a-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1bc7a-104">In questo argomento vengono descritte le impostazioni relative alle scorte e il modo in cui applicarle in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1bc7a-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="1bc7a-105">Overview</span></span>

<span data-ttu-id="1bc7a-106">Le impostazioni relative alle scorte specificano se le scorte devono essere verificate prima di aggiungere prodotti al carrello.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="1bc7a-107">Definiscono inoltre messaggi di merchandising, come "In stock" e "Pochi rimasti".</span><span class="sxs-lookup"><span data-stu-id="1bc7a-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="1bc7a-108">Queste impostazioni assicurano che un prodotto non possa essere acquistato se è esaurito.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="1bc7a-109">Dynamics 365 Commerce fornisce stime della disponibilità dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="1bc7a-110">Per informazioni su come viene calcolata la disponibilità stimata, vedere [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="1bc7a-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="1bc7a-111">In Creazione di siti Web di Commerce, è possibile definire soglie e intervalli di scorte per un prodotto o una categoria.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="1bc7a-112">Queste determinano se le scorte possono essere classificate come in stock, ridotte o esaurite.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="1bc7a-113">Per dettagli, vedere [Configurare buffer e livelli di scorte](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1bc7a-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1bc7a-114">Il supporto per le soglie e gli intervalli di inventario è disponibile in Dynamics 365 Commerce versione 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-114">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="1bc7a-115">Impostazioni relative alle scorte</span><span class="sxs-lookup"><span data-stu-id="1bc7a-115">Inventory settings</span></span>

<span data-ttu-id="1bc7a-116">In Commerce, è possibile definire le impostazioni relative alle scorte selezionando **Impostazioni sito \> Estensioni \> Gestione articoli** in Creazione di siti Web.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-116">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="1bc7a-117">Sono disponibili quattro impostazioni relative alle scorte, una delle quali è obsoleta (deprecata):</span><span class="sxs-lookup"><span data-stu-id="1bc7a-117">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="1bc7a-118">**Abilita controllo scorte su app** - Questa impostazione attiva un controllo delle scorte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-118">**Enable stock check in app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="1bc7a-119">I moduli Casella acquisti, Carrello e Preleva nel punto vendita verificheranno quindi le scorte del prodotto e consentiranno di aggiungere un prodotto al carrello solo se è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-119">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="1bc7a-120">**Livello di scorte basato su** - Questa impostazione definisce come vengono calcolati i livelli di scorte.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-120">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="1bc7a-121">I valori disponibili sono **Totale disponibile**, **Fisico disponibile** e **Soglia esaurito**.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-121">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="1bc7a-122">In Commerce, è possibile definire soglie e intervalli di scorte per ogni prodotto e categoria.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-122">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="1bc7a-123">Le API relative alle scorte restituiscono informazioni sulle scorte del prodotto per le proprietà **Totale disponibile** e **Fisico disponibile**.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-123">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="1bc7a-124">Il rivenditore decide se il valore **Totale disponibile** o **Fisico disponibile** deve essere utilizzato per determinare il conteggio delle scorte e gli intervalli corrispondenti per gli stati In stock o Esaurito.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-124">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="1bc7a-125">Il valore **Soglia esaurito** dell'impostazione **Livello di scorte basato su** è un valore (legacy), obsoleto.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-125">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="1bc7a-126">Quando selezionato, il conteggio delle scorte viene determinato dai risultati del valore **Totale disponibile**, ma la soglia è definita dall'impostazione numerica **Soglia esaurito** descritta in seguito.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-126">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="1bc7a-127">Questa impostazione di soglia si applica a tutti i prodotti in un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-127">This threshold setting applies to all products across an e-commerce site.</span></span> <span data-ttu-id="1bc7a-128">Se le scorte sono inferiori al valore di soglia, un prodotto è considerato esaurito.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-128">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="1bc7a-129">Altrimenti, è considerato in stock.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-129">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="1bc7a-130">Le funzionalità dell'impostazione **Soglia esaurito** sono limitate e non è consigliabile utilizzarla nella versione 10.0.12 e successive.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-130">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="1bc7a-131">**Intervalli scorte** - Questa impostazione definisce gli intervalli delle scorte visualizzati nei moduli del sito.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-131">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="1bc7a-132">È applicabile solo se il valore **Totale disponibile** o il valore **Fisico disponibile** è selezionato per l'impostazione **Livello di scorte basato su**.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-132">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="1bc7a-133">I valori disponibili sono **Tutti**, **Ridotto e esaurito** e **Esaurito**.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-133">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="1bc7a-134">Quando è selezionato **Tutti**, verranno visualizzati tutti gli intervalli di scorte, da In stock (messaggio "Disponibile") a Esaurito (messaggio "Esaurito").</span><span class="sxs-lookup"><span data-stu-id="1bc7a-134">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="1bc7a-135">Quando è selezionato **Ridotto e esaurito**, verranno visualizzati i messaggi di tutti gli intervalli di scorte, ad eccezione di In stock (messaggio "Disponibile").</span><span class="sxs-lookup"><span data-stu-id="1bc7a-135">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="1bc7a-136">Quando è selezionato **Esaurito**, verrà visualizzato solo il messaggio "Esaurito".</span><span class="sxs-lookup"><span data-stu-id="1bc7a-136">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="1bc7a-137">**Soglia esaurito** - Questa vecchia impostazione numerica avrà effetto solo se il valore **Soglia esaurito** è selezionato per l'impostazione **Livello di scorte basato su**.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-137">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="1bc7a-138">Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-138">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="1bc7a-139">Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-139">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="1bc7a-140">Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="1bc7a-140">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="1bc7a-141">Moduli che utilizzano le impostazioni relative alle scorte</span><span class="sxs-lookup"><span data-stu-id="1bc7a-141">Modules that use inventory settings</span></span>

<span data-ttu-id="1bc7a-142">I moduli Casella acquisti, Elenco preferenze, Selettore punto vendita, Carrello e Icona carrello utilizzano le impostazioni relative alle scorte per mostrare gli intervalli e i messaggi delle scorte.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-142">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="1bc7a-143">L'immagine seguente mostra un esempio di pagina dettagli prodotto (PDP) che mostra un messaggio In stock ("Disponibile").</span><span class="sxs-lookup"><span data-stu-id="1bc7a-143">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Esempio di modulo PDP con messaggio In stock](./media/pdp-InStock.png)

<span data-ttu-id="1bc7a-145">L'immagine seguente mostra un esempio di PDP che mostra un messaggio "Esaurito".</span><span class="sxs-lookup"><span data-stu-id="1bc7a-145">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Esempio di modulo PDP con messaggio Esaurito](./media/pdp-outofstock.png)

<span data-ttu-id="1bc7a-147">L'immagine seguente mostra un esempio di carrello che mostra un messaggio In stock ("Disponibile").</span><span class="sxs-lookup"><span data-stu-id="1bc7a-147">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Esempio di modulo Carrello con messaggio In stock](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="1bc7a-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1bc7a-149">Additional resources</span></span>

[<span data-ttu-id="1bc7a-150">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="1bc7a-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1bc7a-151">Configurare buffer scorte e livelli scorte</span><span class="sxs-lookup"><span data-stu-id="1bc7a-151">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="1bc7a-152">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="1bc7a-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="1bc7a-153">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="1bc7a-153">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1bc7a-154">Moduli e pagine gestione conti</span><span class="sxs-lookup"><span data-stu-id="1bc7a-154">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="1bc7a-155">Memorizzare il modulo di selezione</span><span class="sxs-lookup"><span data-stu-id="1bc7a-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="1bc7a-156">SDK e aggiornamenti libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="1bc7a-156">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
