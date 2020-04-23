---
title: Requisiti di impostazione della produzione
description: Questo articolo fornisce informazioni sui requisiti di impostazione per utilizzare un controllo produzione.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 55820d7376750c210d2b7f214f705ffcb222c6cd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212505"
---
# <a name="production-setup-requirements"></a><span data-ttu-id="0a3af-103">Requisiti di impostazione della produzione</span><span class="sxs-lookup"><span data-stu-id="0a3af-103">Production setup requirements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a3af-104">Questo articolo fornisce informazioni sui requisiti di impostazione per utilizzare un controllo produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="0a3af-105">Il controllo produzione è integrato con funzionalità in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="0a3af-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="0a3af-106">Tale interconnettività consente di modificare gli ordini di produzione e di assicurarsi che vengano aggiornati automaticamente in tutti gli altri processi e calcoli correlati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="0a3af-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="0a3af-107">Le procedure di impostazione che seguono dovranno essere completate nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="0a3af-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="0a3af-108">Impostazioni di base obbligatorie in altri moduli</span><span class="sxs-lookup"><span data-stu-id="0a3af-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="0a3af-109">Prima di utilizzare il modulo Controllo produzione è necessario impostare alcune informazioni in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="0a3af-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="0a3af-110">L'impostazione include le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="0a3af-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="0a3af-111">Informazioni generali della società</span><span class="sxs-lookup"><span data-stu-id="0a3af-111">Set up general company information.</span></span>
-   <span data-ttu-id="0a3af-112">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="0a3af-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="0a3af-113">Gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="0a3af-113">Define item groups.</span></span>
-   <span data-ttu-id="0a3af-114">Conti CoGe per i gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="0a3af-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="0a3af-115">Tabella degli articoli di magazzino nella gestione inventario.</span><span class="sxs-lookup"><span data-stu-id="0a3af-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="0a3af-116">Creazione di distinte base e di versioni DBA nel modulo Gestione inventario.</span><span class="sxs-lookup"><span data-stu-id="0a3af-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="0a3af-117">Risorse e calendario obbligatori</span><span class="sxs-lookup"><span data-stu-id="0a3af-117">Required calendar and resource setup</span></span>
<span data-ttu-id="0a3af-118">Prima di utilizzare il modulo Controllo produzione, aprire Amministrazione organizzazione e creare e definire il calendario e le risorse operative nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="0a3af-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="0a3af-119">**Modelli di orario di lavoro**: consente di impostare i modelli di orario di lavoro per definire i tempi disponibili per la programmazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="0a3af-120">**Calendari**: consente di impostare calendari dell'orario di lavoro per definire i giorni dell'anno disponibili per la programmazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="0a3af-121">**Gruppi di risorse**: consente di raggruppare le risorse operative per ottenere una panoramica di tutte le capacità disponibili quando si esegue la programmazione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="0a3af-122">Non è necessario impostare i gruppi di risorse prima di impostare le risorse operative.</span><span class="sxs-lookup"><span data-stu-id="0a3af-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="0a3af-123">Tuttavia, è importante capire come raggruppare le risorse quando si imposta il modulo Controllo produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="0a3af-124">**Risorse**: consente di impostare le risorse operative per definire le risorse utilizzate per completare il processo di produzione e il piano di capacità.</span><span class="sxs-lookup"><span data-stu-id="0a3af-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="0a3af-125">Impostazione dei parametri di produzione obbligatori</span><span class="sxs-lookup"><span data-stu-id="0a3af-125">Required production parameters setup</span></span>
<span data-ttu-id="0a3af-126">**Parametri di controllo produzione**: consente di impostare i parametri di produzione di base per definire la modalità con cui il sistema gestisce ed elabora gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="0a3af-127">Definire la modalità di creazione, valutazione, programmazione e uso degli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="0a3af-128">È inoltre possibile selezionare il genere di riscontro desiderato e il modo in cui la contabilità industriale viene condotta.</span><span class="sxs-lookup"><span data-stu-id="0a3af-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="0a3af-129">Identificazione del nome del giornale</span><span class="sxs-lookup"><span data-stu-id="0a3af-129">Required journal name identification</span></span>
<span data-ttu-id="0a3af-130">**Nomi giornale di registrazione produzione**: consente di specificare i nomi dei giornali di registrazione produzione utilizzati per memorizzare e registrare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="0a3af-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="0a3af-131">Impostazione delle operazioni (se utilizzate)</span><span class="sxs-lookup"><span data-stu-id="0a3af-131">Setup if you use operations</span></span>
<span data-ttu-id="0a3af-132">Le operazioni rappresentano le attività specifiche eseguite per ottenere il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="0a3af-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="0a3af-133">**Nota:** è necessario conoscere i tipi di attività necessarie per preparare l'articolo, nonché l'ordine e le priorità delle attività.</span><span class="sxs-lookup"><span data-stu-id="0a3af-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="0a3af-134">È inoltre necessario conoscere le risorse coinvolte, e la quantità.</span><span class="sxs-lookup"><span data-stu-id="0a3af-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="0a3af-135">**Operazioni**: consente di impostare le operazioni che rappresentano le attività che è necessario completare per produrre l'articolo finito.</span><span class="sxs-lookup"><span data-stu-id="0a3af-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="0a3af-136">**Relazioni**: consente di impostare le relazioni operative per determinare le proprietà dettagliate.</span><span class="sxs-lookup"><span data-stu-id="0a3af-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="0a3af-137">Per definire le relazioni operative, fare clic su **Relazioni** nella pagina **Operazioni**.</span><span class="sxs-lookup"><span data-stu-id="0a3af-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="0a3af-138">Impostazione dei cicli di lavorazione (se utilizzati)</span><span class="sxs-lookup"><span data-stu-id="0a3af-138">Setup if you use routes</span></span>
<span data-ttu-id="0a3af-139">Se si utilizzano i cicli di lavorazione, è necessario definire le operazioni per ogni ciclo di lavorazione produzione impostato.</span><span class="sxs-lookup"><span data-stu-id="0a3af-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="0a3af-140">Il ciclo di lavorazione rappresenta il percorso dell'articolo da un'operazione all'altra, dall'inizio alla fine del processo di produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="0a3af-141">**Categorie costi**: impostare categorie costi per definire il costo orario dei processi specificati e degli orari impostati.</span><span class="sxs-lookup"><span data-stu-id="0a3af-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="0a3af-142">**Gruppi di costi**: impostare gruppi di costi per creare e gestire tipi diversi di determinazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="0a3af-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="0a3af-143">**Gruppi di cicli di lavorazione**: consente di impostare i gruppi di cicli di lavorazione per definire i parametri relativi ai gruppi di cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="0a3af-144">È necessario impostare i gruppi di cicli di lavorazione prima di creare i singoli cicli.</span><span class="sxs-lookup"><span data-stu-id="0a3af-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="0a3af-145">**Cicli di lavorazione**: impostare cicli di lavorazione produzione e definirne le impostazioni predefinite per controllare la programmazione e la determinazione dei costi e dei prezzi delle operazioni dei cicli, nonché le relazioni sullo stato di avanzamento del processo.</span><span class="sxs-lookup"><span data-stu-id="0a3af-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="0a3af-146">**Cicli di lavorazione**: consente di impostare le versioni del ciclo di lavorazione per consentire variazioni dell'articolo nella produzione.</span><span class="sxs-lookup"><span data-stu-id="0a3af-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="0a3af-147">Impostazioni avanzate facoltative</span><span class="sxs-lookup"><span data-stu-id="0a3af-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="0a3af-148">**Gruppi di produzione**: consente di impostare gruppi di produzione per stabilire delle relazioni tra l'ordine di produzione e i conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="0a3af-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="0a3af-149">I conti CoGe sono utilizzati per registrare o raggruppare gli ordini da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="0a3af-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="0a3af-150">**Pool di produzioni**: creare pool di produzioni per raggruppare ordini di produzione allo scopo di elaborare gli ordini di produzione urgenti o eliminare e registrare gruppi di ordini.</span><span class="sxs-lookup"><span data-stu-id="0a3af-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="0a3af-151">**Proprietà**: consente di definire le proprietà per creare gli attributi speciali che è possibile assegnare alle risorse per controllare la sequenza delle produzioni.</span><span class="sxs-lookup"><span data-stu-id="0a3af-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="0a3af-152">Questi attributi sono collegati al modello di orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0a3af-152">These attributes are connected to the working time template.</span></span>




