---
title: "Funzionalità per call center"
description: "Questo articolo fornisce una panoramica delle funzionalità di vendita del servizio clienti in Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 00d24e9933d087f150ec5270da94ad911423824d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="call-center-functionality"></a><span data-ttu-id="8809e-103">Funzionalità del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="8809e-103">Call center functionality</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8809e-104">Questo articolo fornisce una panoramica delle funzionalità di vendita del servizio clienti in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="8809e-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="8809e-105">Dynamics 365 for Retail supporta anche i servizi clienti come un tipo di canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="8809e-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="8809e-106">In un servizio clienti, i lavoratori prendono gli ordini dai clienti per telefono e creano gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="8809e-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="8809e-107">Nella funzionalità del servizio clienti sono incluse le funzioni progettate per semplificare gli ordini per telefono e la gestione dell'assistenza clienti tramite il processo di esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8809e-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="8809e-108">Ad esempio, i lavoratori del servizio clienti possono immettere le informazioni relative ai pagamenti direttamente nell'ordine cliente e possono visualizzare un riepilogo dettagliato delle spese e dei pagamenti prima di inviare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="8809e-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="8809e-109">I dipendenti hanno inoltre a disposizione opzioni per controllare la determinazione del prezzo e possono accedere a vari dati sui clienti, i prodotti e i prezzi dalla pagina **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="8809e-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="8809e-110">Inoltre i call center dispongono di funzionalità avanzate per il monitoraggio dello storico clienti e dello stato degli ordini.</span><span class="sxs-lookup"><span data-stu-id="8809e-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="8809e-111">Ogni servizio clienti può avere propri utenti, metodi di pagamento, gruppi di prezzi, dimensioni finanziarie e modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="8809e-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="8809e-112">È possibile configurare queste opzioni quando si crea il servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="8809e-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="8809e-113">È inoltre possibile utilizzare la pagina **Call center** per attivare o disattivare i seguenti gruppi di funzionalità che sono esclusive dei call center:</span><span class="sxs-lookup"><span data-stu-id="8809e-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="8809e-114">**Completamento ordine** - Questo gruppo include funzionalità correlate ai pagamenti e al completamento degli ordini nella pagina **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="8809e-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="8809e-115">**Vendita diretta** - Questo gruppo include funzionalità che sono correlate ai codici di origine, agli script e alla richieste di catalogo.</span><span class="sxs-lookup"><span data-stu-id="8809e-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="8809e-116">Una volta abilitate nelle impostazioni del call center, queste funzionalità sono disponibili nella pagina **Ordine cliente** agli utenti che sono associati al call center.</span><span class="sxs-lookup"><span data-stu-id="8809e-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="8809e-117">La maggior parte delle funzionalità richiedono una configurazione aggiuntiva prima di poter essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="8809e-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="8809e-118">Prima di poter creare ordini dal call center, è necessario che gli utenti siano aggiunti al call center come utenti del call center.</span><span class="sxs-lookup"><span data-stu-id="8809e-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="8809e-119">Questo passaggio abilita le funzionalità e la configurazione specifica del canale del call center.</span><span class="sxs-lookup"><span data-stu-id="8809e-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="8809e-120">Di seguito sono riportati alcuni esempi delle funzionalità che risultano disponibili:</span><span class="sxs-lookup"><span data-stu-id="8809e-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="8809e-121">La vendita guidata fornisce opzioni di configurazione per gli script di televendita e immagini dei prodotti per aiutare e guidare gli addetti alle vendite nell'acquisizione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="8809e-121">Guided selling provides configuration options for telesales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="8809e-122">Gli ordini non possono essere completati finché gli addetti alle vendite non abbiano acquisito almeno un metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="8809e-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="8809e-123">È possibile configurare le regole di upselling e cross-selling per spingere gli addetti alle vendite a promuovere specifici prodotti presso i clienti.</span><span class="sxs-lookup"><span data-stu-id="8809e-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="8809e-124">Gli addetti alle vendite possono acquisire il codice di origine per il catalogo da cui un cliente sta effettuando l'ordine.</span><span class="sxs-lookup"><span data-stu-id="8809e-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="8809e-125">Gli addetti alle vendite possono aggiungere all'ordine buoni sconto del rivenditore.</span><span class="sxs-lookup"><span data-stu-id="8809e-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="8809e-126">Gli addetti alle vendite possono vendere i programmi di continuità.</span><span class="sxs-lookup"><span data-stu-id="8809e-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="8809e-127">Gli ordini possono essere messi in attesa manualmente o automaticamente, a indicare che occorrono informazioni aggiuntive prima che l'ordine possa essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="8809e-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





