---
title: Panoramica dello sviluppo e della definizione dei contratti di assistenza
description: I contratti di assistenza consentono di definire sia le risorse utilizzate durante un intervento ordinario, sia la modalità di fatturazione di tali risorse a carico del cliente.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae7c3b6e1df9751d886f6eeff778e8045bd7df85
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865947"
---
# <a name="develop-and-establish-service-agreements-overview"></a><span data-ttu-id="67835-103">Panoramica dello sviluppo e della definizione dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="67835-103">Develop and establish service agreements overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67835-104">I contratti di assistenza consentono di definire sia le risorse utilizzate durante un intervento ordinario, sia la modalità di fatturazione di tali risorse a carico del cliente.</span><span class="sxs-lookup"><span data-stu-id="67835-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="67835-105">Ogni contratto di assistenza è associato a un progetto in base al quale viene eseguita la registrazione e la fatturazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="67835-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="67835-106">Tuttavia, è possibile fatturare le transazioni correlate all'ordine di assistenza anche direttamente tramite il progetto, senza associare necessariamente l'ordine di assistenza a un contratto.</span><span class="sxs-lookup"><span data-stu-id="67835-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="67835-107">Questo approccio può rilevarsi utile se l'ordine di assistenza riguarda un intervento occasionale ed è preferibile elaborare rapidamente le transazioni anziché conservare nel tempo i dettagli del cliente contenuti nel contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="67835-108">Contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="67835-108">Service agreement</span></span>

<span data-ttu-id="67835-109">Per ogni contratto di assistenza è necessario specificare un progetto, un ID e un gruppo di contratti di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="67835-110">Quest'ultimo potrà essere utilizzato per ordinare e organizzare i contratti di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="67835-111">Nell'intestazione di un contratto di assistenza sono specificate le impostazioni applicate a tutte le righe del contratto associate:</span><span class="sxs-lookup"><span data-stu-id="67835-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="67835-112">Eventuale sospensione del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="67835-113">Se il contratto è sospeso, non potrà essere utilizzato per generare ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="67835-114">Durata del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="67835-115">Modalità di combinazione delle righe in ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="67835-116">Eventuale configurazione del contratto di assistenza come modello.</span><span class="sxs-lookup"><span data-stu-id="67835-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="67835-117">Nell'intestazione del contratto di assistenza è inoltre possibile impostare tutte le attività di assistenza tecnica e tutti gli oggetti assistenza utilizzabili per il contratto immettendo le attività di assistenza tecnica o gli oggetti assistenza specifici da collegare alle varie righe del contratto.</span><span class="sxs-lookup"><span data-stu-id="67835-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="67835-118">È inoltre possibile utilizzare l'intestazione del contratto di assistenza per copiare le righe del contratto di assistenza o del modello di assistenza nel contratto corrente.</span><span class="sxs-lookup"><span data-stu-id="67835-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="67835-119">È possibile sospendere i contratti di assistenza e interrompere singole righe di un contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="67835-120">Se si seleziona la casella di controllo **Sospeso** in una riga di un contratto di assistenza, non sarà possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="67835-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="67835-121">Creare ordini di assistenza automaticamente o manualmente dal contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="67835-122">Se si seleziona la casella di controllo **Interrotto** in una riga di un contratto di assistenza, non sarà possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="67835-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="67835-123">Creare ordini di assistenza automaticamente o manualmente dalla riga del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="67835-124">Copiare la riga del contratto di assistenza in un altro contratto o ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="67835-125">Se un contratto di assistenza viene sospeso, tutte le righe collegate verranno interrotte indipendentemente dal relativo stato.</span><span class="sxs-lookup"><span data-stu-id="67835-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="67835-126">Righe del contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="67835-126">Service-agreement lines</span></span>

<span data-ttu-id="67835-127">In ogni riga del contratto di assistenza viene descritto dettagliatamente il contenuto dell'intervento di assistenza proposto.</span><span class="sxs-lookup"><span data-stu-id="67835-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="67835-128">Le righe contengono le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="67835-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="67835-129">Tipo di transazione e relativa descrizione.</span><span class="sxs-lookup"><span data-stu-id="67835-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="67835-130">Dipendente che esegue l'intervento di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="67835-131">Oggetti su cui è necessario intervenire in base al contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="67835-132">Frequenza con la quale viene eseguito l'intervento e vengono registrati l'articolo associato, le spese e le transazioni di commissione.</span><span class="sxs-lookup"><span data-stu-id="67835-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="67835-133">Intervallo di tempo in base al quale è possibile raggruppare le righe in un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="67835-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="67835-134">Attività di assistenza tecnica utilizzate per raggruppare set di righe contratto in mansioni e per fornire a tecnici e clienti un riepilogo dell'attività di assistenza da eseguire.</span><span class="sxs-lookup"><span data-stu-id="67835-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="67835-135">Eventuale sospensione della riga.</span><span class="sxs-lookup"><span data-stu-id="67835-135">Whether a line is stopped.</span></span> <span data-ttu-id="67835-136">Non è possibile creare ordini di assistenza per una riga sospesa.</span><span class="sxs-lookup"><span data-stu-id="67835-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="67835-137">Impostazioni del progetto, ad esempio categoria e proprietà riga.</span><span class="sxs-lookup"><span data-stu-id="67835-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67835-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="67835-138">Related topics</span></span>

[<span data-ttu-id="67835-139">Creare contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="67835-139">Create service agreements</span></span>](create-service-agreements.md)
