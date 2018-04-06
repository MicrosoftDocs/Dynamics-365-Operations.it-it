---
title: Gestione magazzino
description: Utilizzare la gestione magazzino per monitorare e automatizzare i processi di magazzino.
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: fc039b3c35c9ff8f40bf671e523104031c598171
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---
# <a name="warehouse-management"></a><span data-ttu-id="ce15a-103">Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="ce15a-103">Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ce15a-104">Il modulo Gestione magazzino per Dynamics 365 for Finance and Operations consente di gestire i processi di magazzino nelle società di produzione, distribuzione e di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="ce15a-104">The Warehouse management module for Dynamics 365 for Finance and Operations lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="ce15a-105">Questo modulo include una vasta gamma di funzionalità per supportare il magazzino a livello ottimale in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ce15a-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="ce15a-106">Il modulo Gestione magazzino è completamente integrato con altri processi aziendali di Finance and Operations, come ad esempio trasporto, produzione, controllo qualità, acquisti, trasferimento, vendite e resi.</span><span class="sxs-lookup"><span data-stu-id="ce15a-106">Warehouse management is fully integrated with other business processes in Finance and Operations such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="ce15a-107">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="ce15a-107">Get started</span></span>
<span data-ttu-id="ce15a-108">Per iniziare a utilizzare Gestione magazzino, è necessario completare l'impostazione dei parametri generali di magazzino per supportare i processi aziendali della società.</span><span class="sxs-lookup"><span data-stu-id="ce15a-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of you company.</span></span>

- <span data-ttu-id="ce15a-109">Andare alla pagina **Parametri di gestione magazzino** in **Gestione magazzino** > **Impostazione** per impostare i parametri generali di magazzino.</span><span class="sxs-lookup"><span data-stu-id="ce15a-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="ce15a-110">È necessario configurare i componenti per i flussi di lavoro in entrata e in uscita dei processi di magazzino in base ai requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="ce15a-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="ce15a-111">I componenti più importanti che è necessario configurare sono i modelli di ondata, i modelli di lavoro, i pool di lavoro e le direttive ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ce15a-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="ce15a-112">Configurazione del magazzino</span><span class="sxs-lookup"><span data-stu-id="ce15a-112">Warehouse configuration</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="ce15a-113">Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="ce15a-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="ce15a-114">Impostare i dispositivi mobili per il lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="ce15a-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="ce15a-115">Impostare una direttiva di ubicazione per lo stoccaggio dell'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="ce15a-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="ce15a-116">Impostare un modello di lavoro per gli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="ce15a-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="ce15a-117">Processi di gestione del magazzino</span><span class="sxs-lookup"><span data-stu-id="ce15a-117">Warehouse management processes</span></span>
- <span data-ttu-id="ce15a-118">Supporto integrato di documenti di origine per ordini cliente, resi, ordini di trasferimento, ordini di produzione e kanban.</span><span class="sxs-lookup"><span data-stu-id="ce15a-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="ce15a-119">Supporto flessibile per flussi di lavoro in entrata e in uscita dei materiali basato su query</span><span class="sxs-lookup"><span data-stu-id="ce15a-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="ce15a-120">Integrazione completa con offerte di trasporto e produzione</span><span class="sxs-lookup"><span data-stu-id="ce15a-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="ce15a-121">Controllo totale dei limiti di stoccaggio ubicazione e delle metriche volume in ubicazione</span><span class="sxs-lookup"><span data-stu-id="ce15a-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="ce15a-122">Proprietà delle scorte controllate in base allo stato inventario</span><span class="sxs-lookup"><span data-stu-id="ce15a-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="ce15a-123">Supporto completo per batch e articoli con numeri di serie</span><span class="sxs-lookup"><span data-stu-id="ce15a-123">Full batch and serial item support</span></span>
- <span data-ttu-id="ce15a-124">Varie funzionalità di ricevimento di articoli</span><span class="sxs-lookup"><span data-stu-id="ce15a-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="ce15a-125">Molteplici strategie di prelievo</span><span class="sxs-lookup"><span data-stu-id="ce15a-125">Multiple picking strategies</span></span>
- <span data-ttu-id="ce15a-126">Supporto integrato per la generazione successiva di lettori di codici a barre</span><span class="sxs-lookup"><span data-stu-id="ce15a-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="ce15a-127">Tipi di contenitori/pallet per processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="ce15a-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="ce15a-128">Funzionalità di conteggio avanzate</span><span class="sxs-lookup"><span data-stu-id="ce15a-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="ce15a-129">Stampa e trasferimento di etichette con il supporto Zebra ZPL</span><span class="sxs-lookup"><span data-stu-id="ce15a-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="ce15a-130">Integrazione di business intelligence in Power BI</span><span class="sxs-lookup"><span data-stu-id="ce15a-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="ce15a-131">Movimento di magazzino manuale e automatico</span><span class="sxs-lookup"><span data-stu-id="ce15a-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="ce15a-132">Controllo qualità completamente integrato (QMS)</span><span class="sxs-lookup"><span data-stu-id="ce15a-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="ce15a-133">Tracciabilità completa della movimentazione materiali dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="ce15a-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="ce15a-134">Elaborazione ondata in uscita</span><span class="sxs-lookup"><span data-stu-id="ce15a-134">Outbound wave processing</span></span>
- <span data-ttu-id="ce15a-135">Supporto per imballaggio manuale e containerizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="ce15a-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="ce15a-136">Prelievo cluster</span><span class="sxs-lookup"><span data-stu-id="ce15a-136">Cluster picking</span></span>
- <span data-ttu-id="ce15a-137">Cross-docking semplice</span><span class="sxs-lookup"><span data-stu-id="ce15a-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce15a-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ce15a-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="ce15a-139">Novità rilasciate e in via di sviluppo</span><span class="sxs-lookup"><span data-stu-id="ce15a-139">What's new and in development</span></span>
<span data-ttu-id="ce15a-140">Passare alla [roadmap di Microsoft Dynamics 365](https://roadmap.dynamics.com/) per un elenco delle nuove funzionalità rilasciate e di quelle che sono in via di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ce15a-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="ce15a-141">Blog</span><span class="sxs-lookup"><span data-stu-id="ce15a-141">Blogs</span></span>
<span data-ttu-id="ce15a-142">Per opinioni, notizie e altre informazioni su Gestione magazzino e altre soluzioni, fare riferimento al [blog di Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog).</span><span class="sxs-lookup"><span data-stu-id="ce15a-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 


