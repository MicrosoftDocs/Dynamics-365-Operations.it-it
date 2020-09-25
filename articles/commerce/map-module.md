---
title: Modulo mappa
description: In questo argomento vengono descritti i moduli mappa e la procedura per configurarli in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ca531e6cbf0a1044b0a13e5cdf42c7b4f0498fe5
ms.sourcegitcommit: 629988f1a704d62648d98649056931b8c33b9e08
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "3811186"
---
# <a name="map-module"></a><span data-ttu-id="a3cdc-103">Modulo mappa</span><span class="sxs-lookup"><span data-stu-id="a3cdc-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="a3cdc-104">In questo argomento vengono descritti i moduli mappa e la procedura per configurarli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a3cdc-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a3cdc-105">Overview</span></span>

<span data-ttu-id="a3cdc-106">Un modulo mappa mostra le posizioni dei punti vendita su una mappa interattiva il cui rendering viene eseguito utilizzando il [controllo Web Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="a3cdc-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="a3cdc-107">È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di commercio in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="a3cdc-108">I moduli mappa offrono viste diverse, come stradale, aerea e Streetside, che gli utenti possono selezionare per visualizzare le posizioni della mappa.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="a3cdc-109">Consentono inoltre interazioni come lo zoom e l'utilizzo della posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="a3cdc-110">Un modulo mappa interagisce con il modulo selettore punto vendita per determinare le posizioni geografiche dei punti vendita che devono essere visualizzati su una mappa.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="a3cdc-111">I moduli mappa e selettore punto vendita interagiscono quando un utente seleziona un punto vendita in uno di questi moduli in una pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="a3cdc-112">I moduli mappa possono essere estesi per altri scenari, oltre all'interazione con i moduli selettore punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="a3cdc-113">Tuttavia, è richiesta la personalizzazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-113">However, module customization is required.</span></span>

<span data-ttu-id="a3cdc-114">Il modulo mappa è stato introdotto in Commerce versione 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-114">The map module was introduced in Commerce version 10.0.13.</span></span>

<span data-ttu-id="a3cdc-115">L'immagine seguente mostra un esempio di modulo mappa utilizzato in una pagina delle posizioni dei punti vendita.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Esempio di un modulo selettore punto vendita](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="a3cdc-117">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="a3cdc-117">Module properties</span></span>

| <span data-ttu-id="a3cdc-118">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="a3cdc-118">Property name</span></span>             | <span data-ttu-id="a3cdc-119">Valore</span><span class="sxs-lookup"><span data-stu-id="a3cdc-119">Value</span></span>                 | <span data-ttu-id="a3cdc-120">descrizione</span><span class="sxs-lookup"><span data-stu-id="a3cdc-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="a3cdc-121">Intestazione</span><span class="sxs-lookup"><span data-stu-id="a3cdc-121">Heading</span></span> | <span data-ttu-id="a3cdc-122">Testo</span><span class="sxs-lookup"><span data-stu-id="a3cdc-122">Text</span></span> | <span data-ttu-id="a3cdc-123">L'intestazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-123">The heading for the module.</span></span> |
| <span data-ttu-id="a3cdc-124">Opzioni puntina: icona predefinita</span><span class="sxs-lookup"><span data-stu-id="a3cdc-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="a3cdc-125">Immagine</span><span class="sxs-lookup"><span data-stu-id="a3cdc-125">Image</span></span> | <span data-ttu-id="a3cdc-126">L'immagine del simbolo della puntina da utilizzare per i punti vendita mostrati su una mappa.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="a3cdc-127">Opzioni puntina: icona attiva</span><span class="sxs-lookup"><span data-stu-id="a3cdc-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="a3cdc-128">Immagine</span><span class="sxs-lookup"><span data-stu-id="a3cdc-128">Image</span></span> | <span data-ttu-id="a3cdc-129">L'immagine del simbolo della puntina da utilizzare per un punto vendita selezionato su una mappa.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="a3cdc-130">Opzioni puntina: colore icona predefinita</span><span class="sxs-lookup"><span data-stu-id="a3cdc-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="a3cdc-131">Stringa di caratteri</span><span class="sxs-lookup"><span data-stu-id="a3cdc-131">Character string</span></span> | <span data-ttu-id="a3cdc-132">Il testo o il valore esadecimale per il colore dei simboli della puntina su una mappa.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="a3cdc-133">Opzioni puntina: colore icona attiva</span><span class="sxs-lookup"><span data-stu-id="a3cdc-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="a3cdc-134">Stringa di caratteri</span><span class="sxs-lookup"><span data-stu-id="a3cdc-134">Character string</span></span> | <span data-ttu-id="a3cdc-135">Il testo o il valore esadecimale per il colore dei simboli della puntina selezionati su una mappa.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="a3cdc-136">Mostra indice</span><span class="sxs-lookup"><span data-stu-id="a3cdc-136">Show index</span></span> | <span data-ttu-id="a3cdc-137">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a3cdc-137">**True** or **False**</span></span> | <span data-ttu-id="a3cdc-138">Se questa proprietà è impostata su **True**, ogni simbolo della puntina che indica un punto vendita mostrerà un indice.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="a3cdc-139">Questo indice corrisponderà all'indice nella visualizzazione elenco mostrata dal modulo selettore punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="a3cdc-140">Aggiungere gli URL di mapping consentiti alle direttive sui criteri di sicurezza dei contenuti di un sito</span><span class="sxs-lookup"><span data-stu-id="a3cdc-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="a3cdc-141">Affinché il modulo mappa interagisca con Bing Maps, è necessario assicurarsi che i seguenti URL di mapping siano consentiti (anche noti come "autorizzati") in base ai criteri di sicurezza dei contenuti (CSP) del sito.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="a3cdc-142">Questa configurazione viene eseguita durante la creazione del sito di Commerce, aggiungendo gli URL consentiti a varie direttive CSP del sito (ad esempio, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="a3cdc-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="a3cdc-143">Per altre informazioni, vedere [Criteri di sicurezza dei contenuti](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="a3cdc-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="a3cdc-144">Alla direttiva **connect-src**, aggiungere **&#42;bing.com**.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="a3cdc-145">Alla direttiva **img-src**, aggiungere **&#42; virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="a3cdc-146">Alla direttiva **script-src**, aggiungere **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="a3cdc-147">Alla direttiva **script style-src**, aggiungere **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="a3cdc-148">Aggiungere un modulo mappa a una pagina</span><span class="sxs-lookup"><span data-stu-id="a3cdc-148">Add a map module to a page</span></span>

<span data-ttu-id="a3cdc-149">Per informazioni dettagliate su come configurare un modulo mappa in una pagina, vedere [Modulo selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="a3cdc-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="a3cdc-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a3cdc-150">Additional resources</span></span>

[<span data-ttu-id="a3cdc-151">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="a3cdc-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a3cdc-152">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="a3cdc-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="a3cdc-153">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="a3cdc-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a3cdc-154">Memorizzare il modulo di selezione</span><span class="sxs-lookup"><span data-stu-id="a3cdc-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="a3cdc-155">Gestire Bing Mappe per la tua organizzazione</span><span class="sxs-lookup"><span data-stu-id="a3cdc-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="a3cdc-156">Controllo Web Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="a3cdc-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
