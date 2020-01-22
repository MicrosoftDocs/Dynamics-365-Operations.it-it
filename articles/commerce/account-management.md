---
title: Pagine e moduli di gestione account
description: In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/02/2019
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
ms.openlocfilehash: f9fc3731cd9d21294b0161e1d419f255096d7790
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885811"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="95f2a-103">Pagine e moduli di gestione account</span><span class="sxs-lookup"><span data-stu-id="95f2a-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="95f2a-104">In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95f2a-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="95f2a-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="95f2a-105">Overview</span></span>

<span data-ttu-id="95f2a-106">La gestione account fa riferimento a un gruppo di pagine utilizzate per gestire informazioni correlate all'account utente in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95f2a-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="95f2a-107">Le pagine di gestione account includono la pagina di destinazione di gestione account e le pagine Profilo utente, Indirizzi utente, Storico ordini, Dettagli ordine, Programma fedeltà e Elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="95f2a-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="95f2a-108">Pagina di destinazione di gestione account</span><span class="sxs-lookup"><span data-stu-id="95f2a-108">Account management landing page</span></span>

<span data-ttu-id="95f2a-109">La pagina di destinazione di gestione account utilizza i seguenti moduli:</span><span class="sxs-lookup"><span data-stu-id="95f2a-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="95f2a-110">**Posizionamento contenuti** - Questo modulo è un modulo contenitore che include tutti i moduli nella pagina di destinazione di gestione account.</span><span class="sxs-lookup"><span data-stu-id="95f2a-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="95f2a-111">**Elemento messaggio di benvenuto account** - Questo modulo viene utilizzato per fornire un messaggio di benvenuto nella pagina di gestione account.</span><span class="sxs-lookup"><span data-stu-id="95f2a-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="95f2a-112">Include proprietà per l'intestazione e le dimensioni dei riquadri.</span><span class="sxs-lookup"><span data-stu-id="95f2a-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="95f2a-113">La proprietà **Dimensioni riquadro** definisce la larghezza del modulo nel modulo Posizionamento contenuti.</span><span class="sxs-lookup"><span data-stu-id="95f2a-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="95f2a-114">I valori vanno da **1** a **12**, dove **12** rappresenta l'intera larghezza del contenitore Posizionamento contenuti.</span><span class="sxs-lookup"><span data-stu-id="95f2a-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="95f2a-115">**Elemento esecuzione ordini account** - Questo modulo viene utilizzato per fornire un riepilogo del numero di ordini effettuati dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="95f2a-116">Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="95f2a-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="95f2a-117">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Storico ordini.</span><span class="sxs-lookup"><span data-stu-id="95f2a-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="95f2a-118">**Elemento posizionamento profilo account** - Questo modulo viene utilizzato per fornire un riepilogo del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="95f2a-119">Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="95f2a-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="95f2a-120">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Profilo utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="95f2a-121">**Elemento elenco preferenze account** - Questo modulo viene utilizzato per fornire un riepilogo degli articoli nell'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="95f2a-122">Ad esempio, potrebbe indicare "L'elenco preferenze contiene 10 articoli".</span><span class="sxs-lookup"><span data-stu-id="95f2a-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="95f2a-123">Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="95f2a-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="95f2a-124">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="95f2a-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="95f2a-125">**Elemento indirizzi account** - Questo modulo viene utilizzato per fornire un riepilogo degli indirizzi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="95f2a-126">Ad esempio, potrebbe indicare "2 indirizzi sono stati aggiunti all'account".</span><span class="sxs-lookup"><span data-stu-id="95f2a-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="95f2a-127">Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli".</span><span class="sxs-lookup"><span data-stu-id="95f2a-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="95f2a-128">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Indirizzi utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="95f2a-129">**Elemento programma fedeltà account** - Questo modulo viene utilizzato per visualizzare e collegare le informazioni sul programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="95f2a-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="95f2a-130">Include proprietà per l'intestazione, le dimensioni dei riquadri, il collegamento "Visualizza dettagli" e il collegamento "Diventa membro".</span><span class="sxs-lookup"><span data-stu-id="95f2a-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="95f2a-131">Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="95f2a-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="95f2a-132">Il collegamento "Diventa membro" deve essere configurato per reindirizzare a una pagina in cui gli utenti possono iscriversi al programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="95f2a-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="95f2a-133">Pagina Storico ordini</span><span class="sxs-lookup"><span data-stu-id="95f2a-133">Order history page</span></span>

<span data-ttu-id="95f2a-134">La pagina Storico ordini utilizza il modulo Storico ordini per visualizzare tutti gli ordini recenti effettuati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="95f2a-135">Pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="95f2a-135">Order details page</span></span>

<span data-ttu-id="95f2a-136">La pagina Dettagli ordine fornisce informazioni dettagliate per ogni ordine ed è accessibile dalla pagina Storico ordini.</span><span class="sxs-lookup"><span data-stu-id="95f2a-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="95f2a-137">Utilizza il modulo Dettagli ordine, che richiede l'ID vendita o l'ID transazione per recuperare i dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="95f2a-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="95f2a-138">Pagina Profilo utente</span><span class="sxs-lookup"><span data-stu-id="95f2a-138">User profile page</span></span>

<span data-ttu-id="95f2a-139">La pagina Profilo utente visualizza i dettagli sull'account utente, ad esempio un nome e un indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-139">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="95f2a-140">Utilizza il modulo Profilo utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-140">It uses the user profile module.</span></span> <span data-ttu-id="95f2a-141">L'indirizzo di posta elettronica non può essere rimosso, ma può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="95f2a-141">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="95f2a-142">La pagina del profilo utente mostra anche le preferenze dell'utente che consentono di attivare o disattivare alcune funzionalità come la personalizzazione degli elenchi dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="95f2a-142">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="95f2a-143">Pagina Indirizzi utente</span><span class="sxs-lookup"><span data-stu-id="95f2a-143">User address page</span></span>

<span data-ttu-id="95f2a-144">La pagina Indirizzi utente visualizza l'elenco degli indirizzi associati all'account utente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-144">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="95f2a-145">L'utente ha fornito tali indirizzi durante il checkout o li ha aggiunti direttamente in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="95f2a-145">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="95f2a-146">Il modulo Indirizzi utente viene utilizzato per aggiungere e modificare gli indirizzi, impostare l'indirizzo principale ed eseguire il rendering degli indirizzi esistenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="95f2a-146">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="95f2a-147">Pagina Elenco preferenze</span><span class="sxs-lookup"><span data-stu-id="95f2a-147">Wish list page</span></span>

<span data-ttu-id="95f2a-148">La pagina Elenco preferenze visualizza gli articoli aggiunti all'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="95f2a-148">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="95f2a-149">Utilizza il modulo Elenco preferenze per eseguire il rendering degli articoli dell'elenco preferenze.</span><span class="sxs-lookup"><span data-stu-id="95f2a-149">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="95f2a-150">Pagina Programma fedeltà</span><span class="sxs-lookup"><span data-stu-id="95f2a-150">Loyalty page</span></span>

<span data-ttu-id="95f2a-151">La pagina Programma fedeltà consente ai clienti di iscriversi a un programma fedeltà oppure, se sono già membri di tale programma, di visualizzare dettagli relativi al programma.</span><span class="sxs-lookup"><span data-stu-id="95f2a-151">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="95f2a-152">Possono inoltre visualizzare i punti che hanno guadagnato e utilizzato nelle ultime transazioni.</span><span class="sxs-lookup"><span data-stu-id="95f2a-152">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95f2a-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="95f2a-153">Additional resources</span></span>

[<span data-ttu-id="95f2a-154">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="95f2a-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="95f2a-155">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="95f2a-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="95f2a-156">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="95f2a-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="95f2a-157">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="95f2a-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="95f2a-158">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="95f2a-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="95f2a-159">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="95f2a-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="95f2a-160">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="95f2a-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="95f2a-161">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="95f2a-161">Footer module</span></span>](author-footer-module.md)
