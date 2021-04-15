---
title: Moduli e pagine gestione conti
description: In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
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
ms.openlocfilehash: df4959a61f1b2948c62a558523a848ff8b2fe0a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796296"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="caec5-103">Moduli e pagine gestione conti</span><span class="sxs-lookup"><span data-stu-id="caec5-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="caec5-104">In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="caec5-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="caec5-105">La gestione account fa riferimento a un gruppo di pagine utilizzate per gestire informazioni correlate all'account utente in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="caec5-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="caec5-106">Le pagine di gestione account includono la pagina di destinazione di gestione account e le pagine Profilo utente, Indirizzi utente, Storico ordini, Dettagli ordine, Programma fedeltà e Elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="caec5-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="caec5-107">Pagina di destinazione di gestione account</span><span class="sxs-lookup"><span data-stu-id="caec5-107">Account management landing page</span></span>

<span data-ttu-id="caec5-108">La pagina di destinazione di gestione account utilizza i seguenti moduli:</span><span class="sxs-lookup"><span data-stu-id="caec5-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="caec5-109">**Contenitore** - Tutti i moduli della pagina di destinazione della gestione di account devono essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="caec5-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="caec5-110">**Riquadro messaggio di benvenuto account** - Questo modulo viene utilizzato per fornire un messaggio di benvenuto nella pagina di gestione account.</span><span class="sxs-lookup"><span data-stu-id="caec5-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="caec5-111">Include proprietà per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="caec5-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="caec5-112">**Riquadro generico account** - Questo modulo può essere utilizzato per fornire intestazioni e collegamenti a pagine di gestione degli account, come le pagine "Storico ordini" o "Profilo".</span><span class="sxs-lookup"><span data-stu-id="caec5-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="caec5-113">Il modulo riquadro generico può essere utilizzato per configurare un riquadro per qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="caec5-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="caec5-114">In Fabrikam, questo modulo viene utilizzato per i collegamenti delle pagine "Storico ordini" e "Profilo" nella pagina di destinazione della gestione dell'account.</span><span class="sxs-lookup"><span data-stu-id="caec5-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="caec5-115">**Riquadro elenco preferenze account** - Questo modulo viene utilizzato per fornire un riepilogo degli articoli nell'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="caec5-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="caec5-116">Ad esempio, potrebbe indicare "L'elenco preferenze contiene 10 articoli".</span><span class="sxs-lookup"><span data-stu-id="caec5-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="caec5-117">Include le proprietà per l'intestazione e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="caec5-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="caec5-118">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="caec5-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="caec5-119">**Riquadro indirizzi account** - Questo modulo viene utilizzato per fornire un riepilogo degli indirizzi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="caec5-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="caec5-120">Ad esempio, potrebbe indicare "2 indirizzi sono stati aggiunti all'account".</span><span class="sxs-lookup"><span data-stu-id="caec5-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="caec5-121">Include le proprietà per l'intestazione e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="caec5-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="caec5-122">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Indirizzi utente.</span><span class="sxs-lookup"><span data-stu-id="caec5-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="caec5-123">**Riquadro programma fedeltà account** - Questo modulo viene utilizzato per visualizzare e collegare informazioni sul programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="caec5-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="caec5-124">Questo riquadro ha due stati: uno mostra i collegamenti per iscriversi a un programma fedeltà se l'utente non è già membro.</span><span class="sxs-lookup"><span data-stu-id="caec5-124">This tile has two states: one state shows links to join a loyalty program if the user is not a member already.</span></span> <span data-ttu-id="caec5-125">L'altro stato mostra i collegamenti per visualizzare la pagina dei dettagli del programma fedeltà quando l'utente è già membro.</span><span class="sxs-lookup"><span data-stu-id="caec5-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="caec5-126">Le proprietà includono l'intestazione, il collegamento "Iscrizione" e il link "Visualizza programma fedeltà".</span><span class="sxs-lookup"><span data-stu-id="caec5-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="caec5-127">Il collegamento "Visualizza programma fedeltà" deve essere configurato per reindirizzare alla pagina Programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="caec5-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="caec5-128">Il collegamento "Iscrizione" deve essere configurato per reindirizzare a una pagina in cui gli utenti possono iscriversi al programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="caec5-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="caec5-129">Pagina Storico ordini</span><span class="sxs-lookup"><span data-stu-id="caec5-129">Order history page</span></span>

<span data-ttu-id="caec5-130">La pagina Storico ordini utilizza il modulo Storico ordini per visualizzare tutti gli ordini recenti effettuati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="caec5-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="caec5-131">Pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="caec5-131">Order details page</span></span>

<span data-ttu-id="caec5-132">La pagina Dettagli ordine fornisce informazioni dettagliate per ogni ordine ed è accessibile dalla pagina Storico ordini.</span><span class="sxs-lookup"><span data-stu-id="caec5-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="caec5-133">Utilizza il modulo Dettagli ordine, che richiede l'ID vendita o l'ID transazione per recuperare i dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="caec5-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="my-profile-page"></a><span data-ttu-id="caec5-134">Pagina profilo</span><span class="sxs-lookup"><span data-stu-id="caec5-134">My profile page</span></span>

<span data-ttu-id="caec5-135">La pagina Profilo personale mostra i dettagli del profilo dell'account utente utilizzando il modulo del profilo dell'account.</span><span class="sxs-lookup"><span data-stu-id="caec5-135">The My profile page shows the user's account profile details using the account profile module.</span></span> <span data-ttu-id="caec5-136">La pagina mostra l'indirizzo e-mail associato all'account utente, nonché le preferenze impostate per l'account.</span><span class="sxs-lookup"><span data-stu-id="caec5-136">The page shows the email address associated with the user's account, as well as preferences set up for the account.</span></span> <span data-ttu-id="caec5-137">Se si impostano attributi cliente personalizzati, anche la sezione "Informazioni aggiuntive" visualizzerà tali attributi.</span><span class="sxs-lookup"><span data-stu-id="caec5-137">If setting up custom customer attributes, an "Additional Information" section will also display those attributes.</span></span> <span data-ttu-id="caec5-138">Gli utenti possono modificare il proprio nome, le preferenze o le informazioni aggiuntive (se disponibili).</span><span class="sxs-lookup"><span data-stu-id="caec5-138">Users can edit their name, preferences, or additional information (if available).</span></span>

### <a name="user-address-page"></a><span data-ttu-id="caec5-139">Pagina Indirizzi utente</span><span class="sxs-lookup"><span data-stu-id="caec5-139">User address page</span></span>

<span data-ttu-id="caec5-140">La pagina Indirizzi utente visualizza l'elenco degli indirizzi associati all'account utente.</span><span class="sxs-lookup"><span data-stu-id="caec5-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="caec5-141">L'utente ha fornito tali indirizzi durante il checkout o li ha aggiunti direttamente in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="caec5-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="caec5-142">Il modulo Indirizzi utente viene utilizzato per aggiungere e modificare gli indirizzi, impostare l'indirizzo principale ed eseguire il rendering degli indirizzi esistenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="caec5-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="caec5-143">Pagina Elenco preferenze</span><span class="sxs-lookup"><span data-stu-id="caec5-143">Wish list page</span></span>

<span data-ttu-id="caec5-144">La pagina Elenco preferenze visualizza gli articoli aggiunti all'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="caec5-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="caec5-145">Utilizza il modulo Elenco preferenze per eseguire il rendering degli articoli dell'elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="caec5-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="caec5-146">Pagina fedeltà</span><span class="sxs-lookup"><span data-stu-id="caec5-146">Loyalty page</span></span>

<span data-ttu-id="caec5-147">La pagina Programma fedeltà consente ai clienti di visualizzare i dettagli sul programma fedeltà se questi sono già membri di tale programma.</span><span class="sxs-lookup"><span data-stu-id="caec5-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="caec5-148">Possono inoltre visualizzare i punti che hanno guadagnato e utilizzato nelle ultime transazioni.</span><span class="sxs-lookup"><span data-stu-id="caec5-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="caec5-149">La pagina utilizza il modulo dettagli programma fedeltà per visualizzare i dettagli del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="caec5-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="caec5-150">Per iscriversi al programma fedeltà, è possibile creare una pagina di marketing con il modulo per l'iscrizione al programma fedeltà e il modulo con i termini di tale programma.</span><span class="sxs-lookup"><span data-stu-id="caec5-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="caec5-151">Se l'utente non è membro di un programma fedeltà, questi moduli consentiranno all'utente di iscriversi.</span><span class="sxs-lookup"><span data-stu-id="caec5-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="caec5-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="caec5-152">Additional resources</span></span>

[<span data-ttu-id="caec5-153">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="caec5-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="caec5-154">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="caec5-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="caec5-155">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="caec5-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="caec5-156">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="caec5-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="caec5-157">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="caec5-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="caec5-158">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="caec5-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="caec5-159">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="caec5-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="caec5-160">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="caec5-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]