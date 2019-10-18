---
title: Funzionalità di vendita del servizio clienti
description: Questo argomento fornisce una panoramica delle funzionalità di vendita del servizio clienti in Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 902db94164b35077a876c8041c038af36561a634
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025773"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="cc754-103">Funzionalità di vendita del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="cc754-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="cc754-104">In Dynamics 365 Retail, un servizio clienti è un tipo di canale di vendita al dettaglio che può essere definito nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc754-104">In Dynamics 365 Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="cc754-105">La definizione di uno specifico canale per le entità del servizio clienti consente al sistema di associare specifici valori predefiniti di dati e di elaborazione di ordini a ordini cliente creati da un utente del canale del servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="cc754-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="cc754-106">Le funzionalità del servizio clienti includono prezzi di vendita al dettaglio e promozioni, cataloghi, gift card e buoni sconto.</span><span class="sxs-lookup"><span data-stu-id="cc754-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="cc754-107">Gli ordini del servizio clienti sono utilizzati dall'applicazione POS per supportare scenari di adempimento ordini multicanale.</span><span class="sxs-lookup"><span data-stu-id="cc754-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="cc754-108">È importante notare che sebbene il modulo servizio clienti possa essere utilizzato da altri settori oltre a quello della vendita al dettaglio, la versione corrente dell'applicazione servizio clienti di Retail non è stata ottimizzata per l'utilizzo in scenari di elaborazione ordini B2B o scenari in cui gli ordini hanno un gran numero di righe di vendita.</span><span class="sxs-lookup"><span data-stu-id="cc754-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="cc754-109">Si consiglia agli utenti che desiderano utilizzare le funzionalità del servizio clienti per l'elaborazione di ordini al di fuori di una tipica elaborazione di transazioni direct-to-consumer di verificare attentamente che l'attivazione della funzionalità di servizio clienti soddisferà le esigenze prestazionali e funzionali.</span><span class="sxs-lookup"><span data-stu-id="cc754-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="cc754-110">Oltre a supportare la creazione di ordini, il modulo servizio clienti fornisce un'applicazione servizio clienti intuitiva che semplifica la ricerca di conti cliente e la verifica di tutti i dati e gli attributi di ordini cliente correlati.</span><span class="sxs-lookup"><span data-stu-id="cc754-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="cc754-111">La schermata del servizio clienti è progettata per consentire a un utente di accedere rapidamente ai dati relativi agli ordini che gli consentiranno di rispondere alle domande sugli ordini più comuni ricevute dai clienti.</span><span class="sxs-lookup"><span data-stu-id="cc754-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="cc754-112">In questa pagina vengono forniti collegamenti alla documentazione su impostazione, configurazione e utilizzo delle funzionalità di servizio clienti in Retail.</span><span class="sxs-lookup"><span data-stu-id="cc754-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Retail.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="cc754-113">Configurazione del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="cc754-113">Configure the call center</span></span>

[<span data-ttu-id="cc754-114">Impostare le opzioni di elaborazione dell'ordine</span><span class="sxs-lookup"><span data-stu-id="cc754-114">Set up order processing options</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="cc754-115">Configurazione dell'elaborazione degli ordini</span><span class="sxs-lookup"><span data-stu-id="cc754-115">Configure order processing</span></span>

[<span data-ttu-id="cc754-116">Impostare avvisi antifrode</span><span class="sxs-lookup"><span data-stu-id="cc754-116">Set up fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="cc754-117">Sospensioni ordine manuali</span><span class="sxs-lookup"><span data-stu-id="cc754-117">Manual Order Holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="cc754-118">Configurazione dell'elaborazione dei pagamenti</span><span class="sxs-lookup"><span data-stu-id="cc754-118">Configure payment processing</span></span>

[<span data-ttu-id="cc754-119">Metodi di pagamento in un servizio clienti</span><span class="sxs-lookup"><span data-stu-id="cc754-119">Payment methods in a call center</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="cc754-120">Configurare le modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="cc754-120">Configure delivery modes</span></span>

[<span data-ttu-id="cc754-121">Configurare le modalità e le spese di consegna del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="cc754-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="cc754-122">Configurazione del direct marketing</span><span class="sxs-lookup"><span data-stu-id="cc754-122">Configure direct marketing</span></span>

[<span data-ttu-id="cc754-123">Cataloghi del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="cc754-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="cc754-124">Impostare l'analisi RFM</span><span class="sxs-lookup"><span data-stu-id="cc754-124">Set up RFM analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="cc754-125">Configurazione di programmi di continuità</span><span class="sxs-lookup"><span data-stu-id="cc754-125">Configure continuity programs</span></span>

[<span data-ttu-id="cc754-126">Impostare un programma di continuità per un servizio clienti</span><span class="sxs-lookup"><span data-stu-id="cc754-126">Set up a continuity program for a call center</span></span>](set-up-continuity-program.md)
