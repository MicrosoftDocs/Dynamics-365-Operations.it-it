---
title: Funzionalità di vendita del servizio clienti
description: Questo argomento fornisce una panoramica delle funzionalità di vendita del servizio clienti in Dynamics 365 Commerce.
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
ms.openlocfilehash: 816bfc8b93f52fe91192874bcc1c8e605e41b582
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023007"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="e349d-103">Funzionalità di vendita del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="e349d-104">In Dynamics 365 Commerce, un servizio clienti è un tipo di canale di commercio che può essere definito nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e349d-104">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="e349d-105">La definizione di uno specifico canale per le entità del servizio clienti consente al sistema di associare specifici valori predefiniti di dati e di elaborazione di ordini a ordini cliente creati da un utente del canale servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="e349d-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="e349d-106">Le funzionalità del servizio clienti includono prezzi e promozioni avanzati, cataloghi, gift card e buoni sconto.</span><span class="sxs-lookup"><span data-stu-id="e349d-106">Call center features include advanced price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="e349d-107">Gli ordini del servizio clienti sono utilizzati dall'applicazione POS per supportare scenari di adempimento ordini multicanale.</span><span class="sxs-lookup"><span data-stu-id="e349d-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="e349d-108">È importante notare che sebbene il modulo servizio clienti possa essere utilizzato da altri settori oltre a quello del commercio, la versione corrente dell'applicazione servizio clienti non è stata ottimizzata per l'utilizzo in scenari di elaborazione ordini B2B o scenari in cui gli ordini hanno un gran numero di righe di vendita.</span><span class="sxs-lookup"><span data-stu-id="e349d-108">It's important to note that while the call center module can be utilized by other industries outside of Commerce, the current release of the call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="e349d-109">Si consiglia agli utenti che desiderano utilizzare le funzionalità del servizio clienti per l'elaborazione di ordini al di fuori di una tipica elaborazione di transazioni direct-to-consumer di verificare attentamente che l'attivazione della funzionalità di servizio clienti soddisferà le esigenze prestazionali e funzionali.</span><span class="sxs-lookup"><span data-stu-id="e349d-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="e349d-110">Oltre a supportare la creazione di ordini, il modulo servizio clienti fornisce un'applicazione servizio clienti intuitiva che semplifica la ricerca di conti cliente e la verifica di tutti i dati e gli attributi di ordini cliente correlati.</span><span class="sxs-lookup"><span data-stu-id="e349d-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="e349d-111">La schermata del servizio clienti è progettata per consentire a un utente di accedere rapidamente ai dati relativi agli ordini che gli consentiranno di rispondere alle domande sugli ordini più comuni ricevute dai clienti.</span><span class="sxs-lookup"><span data-stu-id="e349d-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="e349d-112">In questa pagina vengono forniti collegamenti alla documentazione relativi a impostazione, configurazione e utilizzo delle funzionalità del servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="e349d-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="e349d-113">Configurazione del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-113">Configure the call center</span></span>

[<span data-ttu-id="e349d-114">Impostare canali servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="e349d-115">Configurazione dell'elaborazione degli ordini</span><span class="sxs-lookup"><span data-stu-id="e349d-115">Configure order processing</span></span>

[<span data-ttu-id="e349d-116">Impostazione e utilizzo degli avvisi di frode del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="e349d-117">Configurare e utilizzare le sospensioni degli ordini del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="e349d-118">Configurazione dell'elaborazione dei pagamenti</span><span class="sxs-lookup"><span data-stu-id="e349d-118">Configure payment processing</span></span>

[<span data-ttu-id="e349d-119">Metodi di pagamento nei servizi clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="e349d-120">Configurare le modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="e349d-120">Configure delivery modes</span></span>

[<span data-ttu-id="e349d-121">Configurare le modalità e le spese di consegna del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="e349d-122">Configurazione del direct marketing</span><span class="sxs-lookup"><span data-stu-id="e349d-122">Configure direct marketing</span></span>

[<span data-ttu-id="e349d-123">Cataloghi del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="e349d-124">Impostare l'analisi Recency, Frequency and Monetary (RFM)</span><span class="sxs-lookup"><span data-stu-id="e349d-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="e349d-125">Configurazione di programmi di continuità</span><span class="sxs-lookup"><span data-stu-id="e349d-125">Configure continuity programs</span></span>

[<span data-ttu-id="e349d-126">Impostare programmi di continuità per i servizi clienti</span><span class="sxs-lookup"><span data-stu-id="e349d-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
