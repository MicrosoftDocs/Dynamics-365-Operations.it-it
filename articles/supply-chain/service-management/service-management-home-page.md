---
title: Gestione assistenza
description: Utilizzare Gestione assistenza per stipulare contratti di assistenza e sottoscrizioni di assistenza, gestire ordini di assistenza e richieste di informazioni dei clienti e gestire e analizzare la fornitura di servizi ai clienti.
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: it-it
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="038cc-103">Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="038cc-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="038cc-104">Utilizzare **Gestione assistenza** per stipulare contratti di assistenza e sottoscrizioni di assistenza, gestire ordini di assistenza e richieste di informazioni dei clienti e gestire e analizzare la fornitura di servizi ai clienti.</span><span class="sxs-lookup"><span data-stu-id="038cc-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="038cc-105">I contratti di assistenza consentono di definire le risorse utilizzate durante un intervento ordinario.</span><span class="sxs-lookup"><span data-stu-id="038cc-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="038cc-106">I contratti di assistenza consentono anche di visualizzare la modalità di fatturazione di tali risorse a carico del cliente.</span><span class="sxs-lookup"><span data-stu-id="038cc-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="038cc-107">Un contratto di assistenza può anche comprendere un contratto di servizio che specifica i tempi di risposta standard e offre strumenti per registrare il tempo effettivo.</span><span class="sxs-lookup"><span data-stu-id="038cc-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="038cc-108">È possibile creare ordini di assistenza per gestire informazioni sugli interventi programmati e non programmati eseguiti da un tecnico presso la sede di un cliente.</span><span class="sxs-lookup"><span data-stu-id="038cc-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="038cc-109">Gli ordini di assistenza comprendono informazioni quali:</span><span class="sxs-lookup"><span data-stu-id="038cc-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="038cc-110">le ore di lavoro svolto dal tecnico</span><span class="sxs-lookup"><span data-stu-id="038cc-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="038cc-111">il tipo di assistenza o riparazione</span><span class="sxs-lookup"><span data-stu-id="038cc-111">The type of service or repair</span></span>

3.  <span data-ttu-id="038cc-112">il componente da riparare, compresi dettagli sui sintomi e la diagnosi</span><span class="sxs-lookup"><span data-stu-id="038cc-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="038cc-113">eventuali spese e commissioni associate all'assistenza o alla riparazione</span><span class="sxs-lookup"><span data-stu-id="038cc-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="038cc-114">I clienti possono inviare richieste di assistenza attraverso Internet usando Enterprise Portal.</span><span class="sxs-lookup"><span data-stu-id="038cc-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="038cc-115">È possibile ricevere, elaborare e spedire queste richieste.</span><span class="sxs-lookup"><span data-stu-id="038cc-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="038cc-116">Dopo aver creato un ordine di assistenza, è possibile utilizzare fasi di assistenza per monitorare l'avanzamento e specificare regole che controllano le azioni abilitate in ciascuna fase.</span><span class="sxs-lookup"><span data-stu-id="038cc-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="038cc-117">Una volta completato l'ordine di assistenza, è possibile approvare l'ordine per confermare che è completo e poi registrarlo per avviare il processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="038cc-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="038cc-118">Utilizzare gli strumenti di report per monitorare i margini degli ordini di assistenza e le transazioni di sottoscrizione e stampare le descrizioni del lavoro e i piani di lavoro.</span><span class="sxs-lookup"><span data-stu-id="038cc-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="038cc-119">Processi aziendali</span><span class="sxs-lookup"><span data-stu-id="038cc-119">Business processes</span></span>

<span data-ttu-id="038cc-120">Nel diagramma riportato di seguito vengono illustrati i processi aziendali di alto livello per **Gestione assistenza** e il punto in cui i processi di assistenza si integrano con altri moduli in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="038cc-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="038cc-121">[![Diagramma del processo aziendale Gestione assistenza](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="038cc-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="038cc-122">Uno sguardo a Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="038cc-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="038cc-123">Attività importanti</span><span class="sxs-lookup"><span data-stu-id="038cc-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="038cc-124">Moduli primari</span><span class="sxs-lookup"><span data-stu-id="038cc-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="038cc-125">Report più usati</span><span class="sxs-lookup"><span data-stu-id="038cc-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="038cc-126">Adempimento dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="038cc-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="038cc-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Contratti di assistenza (modulo)</a></span><span class="sxs-lookup"><span data-stu-id="038cc-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="038cc-128"><strong>Margine ordine di assistenza</strong></span><span class="sxs-lookup"><span data-stu-id="038cc-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="038cc-129">Gestione delle richieste di informazioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="038cc-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="038cc-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Ordini di assistenza (modulo)</a></span><span class="sxs-lookup"><span data-stu-id="038cc-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="038cc-131"><strong>Descrizione lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="038cc-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="038cc-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Prospetto interventi (modulo)</a></span><span class="sxs-lookup"><span data-stu-id="038cc-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="038cc-133"><strong>Transazione - Sottoscrizione</strong></span><span class="sxs-lookup"><span data-stu-id="038cc-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="038cc-134"><strong>Transazioni commissione sottoscrizione</strong></span><span class="sxs-lookup"><span data-stu-id="038cc-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="038cc-135">Integrazione di Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="038cc-135">Integration of Service management</span></span>

<span data-ttu-id="038cc-136">Gestione assistenza può essere integrato con i seguenti moduli in Microsoft Dynamics 365 for Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="038cc-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="038cc-137">Vendite e marketing</span><span class="sxs-lookup"><span data-stu-id="038cc-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="038cc-138">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="038cc-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


