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
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7966c6e445e0e44cd4ff8518926aa6b410502e13
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980437"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="4b63b-103">Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico</span><span class="sxs-lookup"><span data-stu-id="4b63b-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4b63b-104">Questa argomento illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="4b63b-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="4b63b-105">Come prerequisito, è necessario creare prima l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="4b63b-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="4b63b-106">Questa procedura è parte delle attività giornaliere per il coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="4b63b-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="4b63b-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="4b63b-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="4b63b-108">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="4b63b-108">Create a sales order</span></span>
1. <span data-ttu-id="4b63b-109">Passare al **pannello di navigazione > Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="4b63b-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-110">Select **New**.</span></span>
3. <span data-ttu-id="4b63b-111">Nel campo **Conto cliente** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4b63b-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4b63b-112">Selezionare il conto **US-004**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="4b63b-113">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-113">Select **OK**.</span></span>
6. <span data-ttu-id="4b63b-114">Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4b63b-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="4b63b-115">Selezionare articolo: **A0001**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-115">Select item **A0001**.</span></span> <span data-ttu-id="4b63b-116">**A0001** è abilitato per la gestione trasporto.</span><span class="sxs-lookup"><span data-stu-id="4b63b-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="4b63b-117">Nel campo **Sito** fare clic sul pulsante a discesa per aprire la ricerca, quindi selezionare un articolo.</span><span class="sxs-lookup"><span data-stu-id="4b63b-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="4b63b-118">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4b63b-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="4b63b-119">Nel campo **Magazzino**, immettere '24' per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="4b63b-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="4b63b-120">Tale magazzino è abilitato per la gestione trasporto e la gestione avanzata del magazzino.</span><span class="sxs-lookup"><span data-stu-id="4b63b-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="4b63b-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-121">Select **Save**.</span></span>
12. <span data-ttu-id="4b63b-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4b63b-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="4b63b-123">Creare un nuovo carico</span><span class="sxs-lookup"><span data-stu-id="4b63b-123">Create a new load</span></span>
1. <span data-ttu-id="4b63b-124">Andare a **Pannello di navigazione > Moduli > Gestione trasporto > Pianificazione > Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="4b63b-125">Selezionare la scheda **Righe di vendita**. Verrà creato il carico per l'ordine cliente creato.</span><span class="sxs-lookup"><span data-stu-id="4b63b-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="4b63b-126">I carichi possono essere creati in base all'offerta e alla domanda da ordini fornitore, ordini di trasferimento e ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4b63b-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="4b63b-127">Nel riquadro azioni fare clic su **Domanda e offerta**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="4b63b-128">Selezionare **Al nuovo carico**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-128">Select **To new load**.</span></span>
5. <span data-ttu-id="4b63b-129">Nel campo **ID modello carico** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4b63b-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="4b63b-130">Il modello di carico definisce le misure massime per il peso e il volume dell'intero carico.</span><span class="sxs-lookup"><span data-stu-id="4b63b-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="4b63b-131">Ad esempio, il modello di carico può rappresentare la dimensione di un container o di un camion.</span><span class="sxs-lookup"><span data-stu-id="4b63b-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="4b63b-132">Selezionare un articolo.</span><span class="sxs-lookup"><span data-stu-id="4b63b-132">Select an item.</span></span>
6. <span data-ttu-id="4b63b-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="4b63b-134">Assegnare una tariffa e un percorso al carico</span><span class="sxs-lookup"><span data-stu-id="4b63b-134">Rate and route the load</span></span>
1. <span data-ttu-id="4b63b-135">Selezionare **Valutazione e distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="4b63b-136">Selezionare **Tariffa workbench ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="4b63b-137">Selezionare **Strumento tariffe**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="4b63b-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4b63b-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="4b63b-139">Selezionare **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-139">Select **Assign**.</span></span>
6. <span data-ttu-id="4b63b-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4b63b-140">Close the page.</span></span>

