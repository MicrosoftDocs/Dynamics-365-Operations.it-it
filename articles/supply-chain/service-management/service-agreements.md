---
title: Contratti di assistenza
description: "I contratti di assistenza consentono di definire sia le risorse utilizzate durante un intervento ordinario, sia la modalità di fatturazione di tali risorse a carico del cliente."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
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
ms.sourcegitcommit: bf9df2a31c758ba6b63ac7952e00065df04552dc
ms.openlocfilehash: aaff0c1d71fcf2656d5d6e76a2bf4b7b3a699281
ms.contentlocale: it-it
ms.lasthandoff: 02/19/2018

---

# <a name="service-agreements"></a><span data-ttu-id="81710-103">Contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="81710-103">Service agreements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="81710-104">I contratti di assistenza consentono di definire sia le risorse utilizzate durante un intervento ordinario, sia la modalità di fatturazione di tali risorse a carico del cliente.</span><span class="sxs-lookup"><span data-stu-id="81710-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="81710-105">Ogni contratto di assistenza è associato a un progetto in base al quale viene eseguita la registrazione e la fatturazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="81710-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="81710-106">Tuttavia, è possibile fatturare le transazioni correlate all'ordine di assistenza anche direttamente tramite il progetto, senza associare necessariamente l'ordine di assistenza a un contratto.</span><span class="sxs-lookup"><span data-stu-id="81710-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="81710-107">Questo approccio può rilevarsi utile se l'ordine di assistenza riguarda un intervento occasionale ed è preferibile elaborare rapidamente le transazioni anziché conservare nel tempo i dettagli del cliente contenuti nel contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="81710-108">Contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="81710-108">Service agreement</span></span>

<span data-ttu-id="81710-109">Per ogni contratto di assistenza è necessario specificare un progetto, un ID e un gruppo di contratti di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="81710-110">Quest'ultimo potrà essere utilizzato per ordinare e organizzare i contratti di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="81710-111">Nell'intestazione di un contratto di assistenza sono specificate le impostazioni applicate a tutte le righe del contratto associate:</span><span class="sxs-lookup"><span data-stu-id="81710-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="81710-112">Eventuale sospensione del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="81710-113">Se il contratto è sospeso, non potrà essere utilizzato per generare ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="81710-114">Durata del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="81710-115">Modalità di combinazione delle righe in ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="81710-116">Eventuale configurazione del contratto di assistenza come modello.</span><span class="sxs-lookup"><span data-stu-id="81710-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="81710-117">Nell'intestazione del contratto di assistenza è inoltre possibile impostare tutte le attività di assistenza tecnica e tutti gli oggetti assistenza utilizzabili per il contratto immettendo le attività di assistenza tecnica o gli oggetti assistenza specifici da collegare alle varie righe del contratto.</span><span class="sxs-lookup"><span data-stu-id="81710-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="81710-118">È inoltre possibile utilizzare l'intestazione del contratto di assistenza per copiare le righe del contratto di assistenza o del modello di assistenza nel contratto corrente.</span><span class="sxs-lookup"><span data-stu-id="81710-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="81710-119">È possibile sospendere i contratti di assistenza e interrompere singole righe di un contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="81710-120">Se si seleziona la casella di controllo **Sospeso** in una riga di un contratto di assistenza, non sarà possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="81710-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="81710-121">Creare ordini di assistenza automaticamente o manualmente dal contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="81710-122">Se si seleziona la casella di controllo **Interrotto** in una riga di un contratto di assistenza, non sarà possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="81710-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="81710-123">Creare ordini di assistenza automaticamente o manualmente dalla riga del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="81710-124">Copiare la riga del contratto di assistenza in un altro contratto o ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="81710-125">Se un contratto di assistenza viene sospeso, tutte le righe collegate verranno interrotte indipendentemente dal relativo stato.</span><span class="sxs-lookup"><span data-stu-id="81710-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="81710-126">Righe del contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="81710-126">Service-agreement lines</span></span>

<span data-ttu-id="81710-127">In ogni riga del contratto di assistenza viene descritto dettagliatamente il contenuto dell'intervento di assistenza proposto.</span><span class="sxs-lookup"><span data-stu-id="81710-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="81710-128">Le righe contengono le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="81710-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="81710-129">Tipo di transazione e relativa descrizione.</span><span class="sxs-lookup"><span data-stu-id="81710-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="81710-130">Dipendente che esegue l'intervento di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="81710-131">Oggetti su cui è necessario intervenire in base al contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="81710-132">Frequenza con la quale viene eseguito l'intervento e vengono registrati l'articolo associato, le spese e le transazioni di commissione.</span><span class="sxs-lookup"><span data-stu-id="81710-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="81710-133">Intervallo di tempo in base al quale è possibile raggruppare le righe in un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="81710-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="81710-134">Attività di assistenza tecnica utilizzate per raggruppare set di righe contratto in mansioni e per fornire a tecnici e clienti un riepilogo dell'attività di assistenza da eseguire.</span><span class="sxs-lookup"><span data-stu-id="81710-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="81710-135">Eventuale sospensione della riga.</span><span class="sxs-lookup"><span data-stu-id="81710-135">Whether a line is stopped.</span></span> <span data-ttu-id="81710-136">Non è possibile creare ordini di assistenza per una riga sospesa.</span><span class="sxs-lookup"><span data-stu-id="81710-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="81710-137">Impostazioni del progetto, ad esempio categoria e proprietà riga.</span><span class="sxs-lookup"><span data-stu-id="81710-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81710-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="81710-138">Related topics</span></span>

[<span data-ttu-id="81710-139">Creare contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="81710-139">Create service agreements</span></span>](create-service-agreements.md)

