---
title: Pagine e moduli di gestione account
description: In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/23/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8787a7b01ecf15752569d2a3a8d7804fe492e63d
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025702"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="18a08-103">Pagine e moduli di gestione account</span><span class="sxs-lookup"><span data-stu-id="18a08-103">Account management pages and modules</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="18a08-104">In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="18a08-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="18a08-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="18a08-105">Overview</span></span>

<span data-ttu-id="18a08-106">La gestione account fa riferimento a un gruppo di pagine utilizzate per gestire informazioni correlate all'account utente in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="18a08-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="18a08-107">Le pagine di gestione account includono la pagina di destinazione di gestione account e le pagine Profilo utente, Indirizzi utente, Storico ordini, Dettagli ordine, Programma fedeltà e Elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="18a08-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="18a08-108">Pagina di destinazione di gestione account</span><span class="sxs-lookup"><span data-stu-id="18a08-108">Account management landing page</span></span>

<span data-ttu-id="18a08-109">La pagina di destinazione di gestione account utilizza i seguenti moduli:</span><span class="sxs-lookup"><span data-stu-id="18a08-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="18a08-110">**Contenitore** - Tutti i moduli della pagina di destinazione della gestione di account devono essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="18a08-110">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="18a08-111">**Riquadro messaggio di benvenuto account** - Questo modulo viene utilizzato per fornire un messaggio di benvenuto nella pagina di gestione account.</span><span class="sxs-lookup"><span data-stu-id="18a08-111">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="18a08-112">Include proprietà per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="18a08-112">It includes properties for the heading.</span></span>
- <span data-ttu-id="18a08-113">**Riquadro generico account** - Questo modulo può essere utilizzato per fornire intestazioni e collegamenti a pagine di gestione degli account, come le pagine "Storico ordini" o "Profilo".</span><span class="sxs-lookup"><span data-stu-id="18a08-113">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="18a08-114">Il modulo riquadro generico può essere utilizzato per configurare un riquadro per qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="18a08-114">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="18a08-115">In Fabrikam, questo modulo viene utilizzato per i collegamenti delle pagine "Storico ordini" e "Profilo" nella pagina di destinazione della gestione dell'account.</span><span class="sxs-lookup"><span data-stu-id="18a08-115">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="18a08-116">**Riquadro elenco preferenze account** - Questo modulo viene utilizzato per fornire un riepilogo degli articoli nell'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="18a08-116">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="18a08-117">Ad esempio, potrebbe indicare "L'elenco preferenze contiene 10 articoli".</span><span class="sxs-lookup"><span data-stu-id="18a08-117">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="18a08-118">Include le proprietà per l'intestazione e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="18a08-118">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="18a08-119">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="18a08-119">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="18a08-120">**Riquadro indirizzi account** - Questo modulo viene utilizzato per fornire un riepilogo degli indirizzi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="18a08-120">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="18a08-121">Ad esempio, potrebbe indicare "2 indirizzi sono stati aggiunti all'account".</span><span class="sxs-lookup"><span data-stu-id="18a08-121">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="18a08-122">Include le proprietà per l'intestazione e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="18a08-122">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="18a08-123">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Indirizzi utente.</span><span class="sxs-lookup"><span data-stu-id="18a08-123">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="18a08-124">**Riquadro programma fedeltà account** - Questo modulo viene utilizzato per visualizzare e collegare informazioni sul programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="18a08-124">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="18a08-125">Questo riquadro ha due stati: uno mostra i collegamenti per iscriversi a un programma fedeltà se l'utente non è già membro.</span><span class="sxs-lookup"><span data-stu-id="18a08-125">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="18a08-126">L'altro stato mostra i collegamenti per visualizzare la pagina dei dettagli del programma fedeltà quando l'utente è già membro.</span><span class="sxs-lookup"><span data-stu-id="18a08-126">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="18a08-127">Le proprietà includono l'intestazione, il collegamento "Iscrizione" e il link "Visualizza programma fedeltà".</span><span class="sxs-lookup"><span data-stu-id="18a08-127">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="18a08-128">Il collegamento "Visualizza programma fedeltà" deve essere configurato per reindirizzare alla pagina Programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="18a08-128">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="18a08-129">Il collegamento "Iscrizione" deve essere configurato per reindirizzare a una pagina in cui gli utenti possono iscriversi al programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="18a08-129">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="18a08-130">Pagina Storico ordini</span><span class="sxs-lookup"><span data-stu-id="18a08-130">Order history page</span></span>

<span data-ttu-id="18a08-131">La pagina Storico ordini utilizza il modulo Storico ordini per visualizzare tutti gli ordini recenti effettuati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="18a08-131">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="18a08-132">Pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="18a08-132">Order details page</span></span>

<span data-ttu-id="18a08-133">La pagina Dettagli ordine fornisce informazioni dettagliate per ogni ordine ed è accessibile dalla pagina Storico ordini.</span><span class="sxs-lookup"><span data-stu-id="18a08-133">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="18a08-134">Utilizza il modulo Dettagli ordine, che richiede l'ID vendita o l'ID transazione per recuperare i dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="18a08-134">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="18a08-135">Pagina Profilo utente</span><span class="sxs-lookup"><span data-stu-id="18a08-135">User profile page</span></span>

<span data-ttu-id="18a08-136">La pagina Profilo utente visualizza i dettagli sull'account utente, ad esempio un nome e un indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="18a08-136">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="18a08-137">Utilizza i dettagli del profilo utente e i moduli di modifica del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="18a08-137">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="18a08-138">L'indirizzo di posta elettronica non può essere rimosso, ma può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="18a08-138">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="18a08-139">La pagina del profilo utente mostra anche le preferenze dell'utente che consentono di attivare o disattivare alcune funzionalità come la personalizzazione degli elenchi dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="18a08-139">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="18a08-140">Pagina Indirizzi utente</span><span class="sxs-lookup"><span data-stu-id="18a08-140">User address page</span></span>

<span data-ttu-id="18a08-141">La pagina Indirizzi utente visualizza l'elenco degli indirizzi associati all'account utente.</span><span class="sxs-lookup"><span data-stu-id="18a08-141">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="18a08-142">L'utente ha fornito tali indirizzi durante il checkout o li ha aggiunti direttamente in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="18a08-142">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="18a08-143">Il modulo Indirizzi utente viene utilizzato per aggiungere e modificare gli indirizzi, impostare l'indirizzo principale ed eseguire il rendering degli indirizzi esistenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="18a08-143">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="18a08-144">Pagina Elenco preferenze</span><span class="sxs-lookup"><span data-stu-id="18a08-144">Wish list page</span></span>

<span data-ttu-id="18a08-145">La pagina Elenco preferenze visualizza gli articoli aggiunti all'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="18a08-145">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="18a08-146">Utilizza il modulo Elenco preferenze per eseguire il rendering degli articoli dell'elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="18a08-146">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="18a08-147">Pagina fedeltà</span><span class="sxs-lookup"><span data-stu-id="18a08-147">Loyalty page</span></span>

<span data-ttu-id="18a08-148">La pagina Programma fedeltà consente ai clienti di visualizzare i dettagli sul programma fedeltà se questi sono già membri di tale programma.</span><span class="sxs-lookup"><span data-stu-id="18a08-148">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="18a08-149">Possono inoltre visualizzare i punti che hanno guadagnato e utilizzato nelle ultime transazioni.</span><span class="sxs-lookup"><span data-stu-id="18a08-149">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="18a08-150">La pagina utilizza il modulo dettagli programma fedeltà per visualizzare i dettagli del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="18a08-150">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="18a08-151">Per iscriversi al programma fedeltà, è possibile creare una pagina di marketing con il modulo per l'iscrizione al programma fedeltà e il modulo con i termini di tale programma.</span><span class="sxs-lookup"><span data-stu-id="18a08-151">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="18a08-152">Se l'utente non è membro di un programma fedeltà, questi moduli consentiranno all'utente di iscriversi.</span><span class="sxs-lookup"><span data-stu-id="18a08-152">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="18a08-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="18a08-153">Additional resources</span></span>

[<span data-ttu-id="18a08-154">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="18a08-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="18a08-155">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="18a08-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="18a08-156">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="18a08-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="18a08-157">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="18a08-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="18a08-158">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="18a08-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="18a08-159">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="18a08-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="18a08-160">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="18a08-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="18a08-161">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="18a08-161">Footer module</span></span>](author-footer-module.md)
