---
title: Rilasciare gli ordini di produzione
description: "Un ordine di produzione rilasciato è un ordine che è stato autorizzato per la produzione. Il termine Rilasciato viene utilizzato per descrivere uno stato del ciclo di vita dell'ordine di produzione, quando l'ordine di produzione è disponibile per l'esecuzione nello shop floor di produzione e per i processi di magazzino."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 400c2786d80681827829286e6e9667b4d51612c4
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="release-production-orders"></a><span data-ttu-id="ae7b4-104">Rilasciare gli ordini di produzione</span><span class="sxs-lookup"><span data-stu-id="ae7b4-104">Release production orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae7b4-105">Un ordine di produzione rilasciato è un ordine che è stato autorizzato per la produzione.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="ae7b4-106">Il termine Rilasciato viene utilizzato per descrivere uno stato del ciclo di vita dell'ordine di produzione, quando l'ordine di produzione è disponibile per l'esecuzione nello shop floor di produzione e per i processi di magazzino.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span> 

<a name="characteristics-of-the-released-state"></a><span data-ttu-id="ae7b4-107">Caratteristiche dello stato Rilasciato</span><span class="sxs-lookup"><span data-stu-id="ae7b4-107">Characteristics of the Released state</span></span>
-------------------------------------

<span data-ttu-id="ae7b4-108">Lo stato **Rilasciato** è uno stato del ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="ae7b4-109">Gli ordini di produzione nello stato **Rilasciato** sono disponibili per l'esecuzione nello shop floor di produzione e per i processi di magazzino.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="ae7b4-110">Lo stato **Rilasciato** ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae7b4-110">The **Released** state has the following characteristics:</span></span>

-   <span data-ttu-id="ae7b4-111">Lo stato di un ordine di produzione può essere impostato su **Rilasciato** dall'ordine di produzione stesso o utilizzando un processo batch.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="ae7b4-112">L'ordine di produzione può anche essere aggiornato automaticamente negli ordini di produzione pianificati che vengono consolidati utilizzando il campo **Intervallo temporale stabilizzazione** nella pagina **Piano generale**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
-   <span data-ttu-id="ae7b4-113">Lo stato **Rilasciato** indica agli operatori dello shop floor (operatori) di avviare l'esecuzione dei processi di produzione nello shop floor.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
-   <span data-ttu-id="ae7b4-114">I documenti di produzione, ad esempio schede del ciclo di lavorazione, processi di cicli di lavorazione e schede processi, forniscono informazioni sui processi di produzione e possono essere emessi.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
-   <span data-ttu-id="ae7b4-115">Per i materiali che vengono prenotati fisicamente, viene generato lavoro di magazzino per prelevare materiali per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="ae7b4-116">Rilascio dei processi nel reparto produzione</span><span class="sxs-lookup"><span data-stu-id="ae7b4-116">Releasing jobs to the shop floor</span></span>
<span data-ttu-id="ae7b4-117">Dopo che un ordine di produzione viene rilasciato, i processi di produzione correlati all'ordine sono visibili e pronti per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="ae7b4-118">Gli operatori possono effettuare le registrazioni dei processi, ad esempio l'avvio, l'interruzione e il completamento, nella pagina **Terminale schede processi** o nella pagina **Dispositivo schede processo**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="ae7b4-119">Le informazioni su ora e quantità registrate verranno trasferite automaticamente dalle pagine di registrazione ai giornali di registrazione produzione per tenere traccia del tempo e della quantità consumati.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="ae7b4-120">Schede del ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="ae7b4-120">Route cards</span></span>
<span data-ttu-id="ae7b4-121">Una scheda ciclo di lavorazione fornisce una panoramica delle informazioni di impostazione del ciclo di lavorazione e delle operazioni e dei metodi di programmazione delle operazioni e dei processi.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="ae7b4-122">Processi cicli di lavorazione</span><span class="sxs-lookup"><span data-stu-id="ae7b4-122">Route jobs</span></span>
<span data-ttu-id="ae7b4-123">Un processo del ciclo di lavorazione elenca ciascun processo di un'operazione in dettaglio e include i tempi di attrezzaggio, elaborazione, attesa e trasporto.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="ae7b4-124">Ad esempio, un'operazione come la verniciatura, può richiedere singoli processi, quali il tempo di attrezzaggio, il tempo di esecuzione della verniciatura e il tempo di attesa per l'asciugatura.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="ae7b4-125">Schede processi</span><span class="sxs-lookup"><span data-stu-id="ae7b4-125">Job cards</span></span>
<span data-ttu-id="ae7b4-126">In una scheda processo sono elencati i singoli processi di una particolare operazione.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="ae7b4-127">Viene visualizzato un processo per pagina.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-127">One job appears on each page.</span></span> <span data-ttu-id="ae7b4-128">I processi inclusi in una scheda processi e i relativi tempi stimati derivano dalle informazioni di impostazione dei cicli di lavorazione e delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="ae7b4-129">In una scheda processo, è possibile aprire **Righe giornale di registrazione produzione**, **scheda processo**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="ae7b4-130">Il responsabile delle risorse operative fornisce un riscontro sul processo di produzione.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="ae7b4-131">In alcuni campi è possibile immettere le statistiche sui consumi e informazioni quali la quantità difettosa.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="ae7b4-132">Lavoro di magazzino per il prelievo di materie prime</span><span class="sxs-lookup"><span data-stu-id="ae7b4-132">Warehouse work for raw material picking</span></span>
<span data-ttu-id="ae7b4-133">Il lavoro per il prelievo delle materie prime viene generato durante il rilascio.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="ae7b4-134">Il lavoro viene generato solo per la quantità di materiale fisicamente prenotata per l'ordine di produzione prima che l'ordine è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="ae7b4-135">La seguente impostazione è necessaria per generare il lavoro del magazzino per il prelievo di materie prime:</span><span class="sxs-lookup"><span data-stu-id="ae7b4-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

-   <span data-ttu-id="ae7b4-136">Una direttiva di ubicazione per il prelievo delle materie prime che determina l'ubicazione di magazzino da cui prelevare i materiali</span><span class="sxs-lookup"><span data-stu-id="ae7b4-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
-   <span data-ttu-id="ae7b4-137">Un modello di ondata per le materie prime, in cui sono configurati i criteri per l'esecuzione di lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="ae7b4-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
-   <span data-ttu-id="ae7b4-138">Un'ubicazione di entrata produzione che determina l'ubicazione in cui stoccare i materiali</span><span class="sxs-lookup"><span data-stu-id="ae7b4-138">A production input location that determines where materials are put</span></span>





