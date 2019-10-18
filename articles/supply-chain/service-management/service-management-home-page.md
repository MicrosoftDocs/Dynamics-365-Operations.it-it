---
title: Panoramica di Gestione assistenza
description: Utilizzare Gestione assistenza per stipulare contratti di assistenza e sottoscrizioni di assistenza, gestire ordini di assistenza e richieste di informazioni dei clienti e gestire e analizzare la fornitura di servizi ai clienti.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd2f27c5797fbd34674e39013ed3e0e40cdb28b2
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251134"
---
# <a name="service-management-overview"></a><span data-ttu-id="1f967-103">Panoramica di Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1f967-104">Utilizzare **Gestione assistenza** per stipulare contratti di assistenza e sottoscrizioni di assistenza, gestire ordini di assistenza e richieste di informazioni dei clienti e gestire e analizzare la fornitura di servizi ai clienti.</span><span class="sxs-lookup"><span data-stu-id="1f967-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="1f967-105">I contratti di assistenza consentono di definire le risorse utilizzate durante un intervento ordinario.</span><span class="sxs-lookup"><span data-stu-id="1f967-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="1f967-106">I contratti di assistenza consentono anche di visualizzare la modalità di fatturazione di tali risorse a carico del cliente.</span><span class="sxs-lookup"><span data-stu-id="1f967-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="1f967-107">Un contratto di assistenza può anche comprendere un contratto di servizio che specifica i tempi di risposta standard e offre strumenti per registrare il tempo effettivo.</span><span class="sxs-lookup"><span data-stu-id="1f967-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="1f967-108">È possibile creare ordini di assistenza per gestire informazioni sugli interventi programmati e non programmati eseguiti da un tecnico presso la sede di un cliente.</span><span class="sxs-lookup"><span data-stu-id="1f967-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="1f967-109">Gli ordini di assistenza comprendono informazioni quali:</span><span class="sxs-lookup"><span data-stu-id="1f967-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="1f967-110">le ore di lavoro svolto dal tecnico</span><span class="sxs-lookup"><span data-stu-id="1f967-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="1f967-111">il tipo di assistenza o riparazione</span><span class="sxs-lookup"><span data-stu-id="1f967-111">The type of service or repair</span></span>

3.  <span data-ttu-id="1f967-112">il componente da riparare, compresi dettagli sui sintomi e la diagnosi</span><span class="sxs-lookup"><span data-stu-id="1f967-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="1f967-113">eventuali spese e commissioni associate all'assistenza o alla riparazione</span><span class="sxs-lookup"><span data-stu-id="1f967-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="1f967-114">È possibile ricevere, elaborare e spedire richieste di assistenza.</span><span class="sxs-lookup"><span data-stu-id="1f967-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="1f967-115">Dopo aver creato un ordine di assistenza, è possibile utilizzare fasi di assistenza per monitorare l'avanzamento e specificare regole che controllano le azioni abilitate in ciascuna fase.</span><span class="sxs-lookup"><span data-stu-id="1f967-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="1f967-116">Una volta completato l'ordine di assistenza, è possibile approvare l'ordine per confermare che è completo e poi registrarlo per avviare il processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="1f967-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="1f967-117">Utilizzare gli strumenti di report per monitorare i margini degli ordini di assistenza e le transazioni di sottoscrizione e stampare le descrizioni del lavoro e i piani di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1f967-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="1f967-118">Processi aziendali</span><span class="sxs-lookup"><span data-stu-id="1f967-118">Business processes</span></span>

<span data-ttu-id="1f967-119">Nel diagramma riportato di seguito vengono illustrati i processi aziendali di alto livello per **Gestione assistenza** e il punto in cui i processi di assistenza si integrano con altri moduli.</span><span class="sxs-lookup"><span data-stu-id="1f967-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="1f967-120">[![Diagramma del processo aziendale Gestione assistenza](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="1f967-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="1f967-121">Uno sguardo a Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-121">Service management at a glance</span></span>

|<span data-ttu-id="1f967-122">Attività importanti</span><span class="sxs-lookup"><span data-stu-id="1f967-122">Important tasks</span></span>           | <span data-ttu-id="1f967-123">Pagine principali</span><span class="sxs-lookup"><span data-stu-id="1f967-123">Primary pages</span></span>                         |<span data-ttu-id="1f967-124">Report più usati</span><span class="sxs-lookup"><span data-stu-id="1f967-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="1f967-125">Adempimento dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-125">Fulfill service agreements</span></span>|<span data-ttu-id="1f967-126">Contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-126">Service agreements</span></span>                     |<span data-ttu-id="1f967-127">Margine ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-127">Service order margin</span></span>         |
|<span data-ttu-id="1f967-128">Gestione delle richieste di informazioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="1f967-128">Handle customer inquiries</span></span> |<span data-ttu-id="1f967-129">Ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-129">Service orders</span></span>                         |<span data-ttu-id="1f967-130">Descrizione lavoro</span><span class="sxs-lookup"><span data-stu-id="1f967-130">Work description</span></span>             |
|                          |<span data-ttu-id="1f967-131">Prospetto interventi</span><span class="sxs-lookup"><span data-stu-id="1f967-131">Dispatch board</span></span>                         |<span data-ttu-id="1f967-132">Transazione - Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="1f967-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="1f967-133">Transazioni commissione sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="1f967-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="1f967-134">Integrazione di Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="1f967-134">Integration of Service management</span></span>

<span data-ttu-id="1f967-135">Gstione assistenza può essere integrato con i seguenti moduli:</span><span class="sxs-lookup"><span data-stu-id="1f967-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="1f967-136">Vendite e marketing</span><span class="sxs-lookup"><span data-stu-id="1f967-136">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="1f967-137">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="1f967-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

