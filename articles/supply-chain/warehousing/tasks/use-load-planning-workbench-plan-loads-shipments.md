---
title: Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico
description: Questa argomento illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c37a98a3728cb1233a6e1207975a6b8f23f8120d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431528"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="1e0cb-103">Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico</span><span class="sxs-lookup"><span data-stu-id="1e0cb-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e0cb-104">Questa argomento illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="1e0cb-105">Come prerequisito, è necessario creare prima l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="1e0cb-106">Questa procedura è parte delle attività giornaliere per il coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="1e0cb-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="1e0cb-108">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="1e0cb-108">Create a sales order</span></span>
1. <span data-ttu-id="1e0cb-109">Passare al **pannello di navigazione > Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="1e0cb-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-110">Select **New**.</span></span>
3. <span data-ttu-id="1e0cb-111">Nel campo **Conto cliente** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1e0cb-112">Selezionare il conto **US-004**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="1e0cb-113">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-113">Select **OK**.</span></span>
6. <span data-ttu-id="1e0cb-114">Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="1e0cb-115">Selezionare articolo: **A0001**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-115">Select item **A0001**.</span></span> <span data-ttu-id="1e0cb-116">**A0001** è abilitato per la gestione trasporto.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="1e0cb-117">Nel campo **Sito** fare clic sul pulsante a discesa per aprire la ricerca, quindi selezionare un articolo.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="1e0cb-118">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="1e0cb-119">Nel campo **Magazzino**, immettere '24' per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="1e0cb-120">Tale magazzino è abilitato per la gestione trasporto e la gestione avanzata del magazzino.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="1e0cb-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-121">Select **Save**.</span></span>
12. <span data-ttu-id="1e0cb-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="1e0cb-123">Creare un nuovo carico</span><span class="sxs-lookup"><span data-stu-id="1e0cb-123">Create a new load</span></span>
1. <span data-ttu-id="1e0cb-124">Andare a **Pannello di navigazione > Moduli > Gestione trasporto > Pianificazione > Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="1e0cb-125">Selezionare la scheda **Righe di vendita**. Verrà creato il carico per l'ordine cliente creato.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="1e0cb-126">I carichi possono essere creati in base all'offerta e alla domanda da ordini fornitore, ordini di trasferimento e ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="1e0cb-127">Nel riquadro azioni fare clic su **Domanda e offerta**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="1e0cb-128">Selezionare **Al nuovo carico**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-128">Select **To new load**.</span></span>
5. <span data-ttu-id="1e0cb-129">Nel campo **ID modello carico** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="1e0cb-130">Il modello di carico definisce le misure massime per il peso e il volume dell'intero carico.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="1e0cb-131">Ad esempio, il modello di carico può rappresentare la dimensione di un container o di un camion.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="1e0cb-132">Selezionare un articolo.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-132">Select an item.</span></span>
6. <span data-ttu-id="1e0cb-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="1e0cb-134">Assegnare una tariffa e un percorso al carico</span><span class="sxs-lookup"><span data-stu-id="1e0cb-134">Rate and route the load</span></span>
1. <span data-ttu-id="1e0cb-135">Selezionare **Valutazione e distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="1e0cb-136">Selezionare **Tariffa workbench ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="1e0cb-137">Selezionare **Strumento tariffe**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="1e0cb-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="1e0cb-139">Selezionare **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-139">Select **Assign**.</span></span>
6. <span data-ttu-id="1e0cb-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-140">Close the page.</span></span>

