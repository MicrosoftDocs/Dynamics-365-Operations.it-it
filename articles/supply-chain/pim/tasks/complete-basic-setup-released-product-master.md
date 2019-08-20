---
title: Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata
description: Questo argomento procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd7e02c9aea17fbc3312660d0e50cd8bbf39aa3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845019"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="7f6ee-103">Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata</span><span class="sxs-lookup"><span data-stu-id="7f6ee-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7f6ee-104">Questo argomento procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="7f6ee-105">Questa è la terza procedura di otto che illustra come sviluppare le combinazioni per la configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="7f6ee-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7f6ee-107">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="7f6ee-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="7f6ee-109">Selezionare la rappresentazione generale prodotto che è stata rilasciata nella seconda procedura.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="7f6ee-110">La rappresentazione generale prodotto viene creata con la tecnologia di configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="7f6ee-111">Nel riquadro azioni fare clic su **Prodotto**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="7f6ee-112">Fare clic su **Gruppi di dimensioni** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="7f6ee-113">Nel campo **Gruppo di dimensioni di immagazzinamento** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7f6ee-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="7f6ee-115">Il gruppo dimensione di immagazzinamento determina quali dimensioni di immagazzinamento vengono utilizzate per la transazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="7f6ee-116">Selezionare **Sito** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="7f6ee-117">Nel campo **Gruppo di dimensioni di tracciabilità** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="7f6ee-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="7f6ee-119">Il gruppo dimensione di tracciabilità determina quali dimensioni di tracciabilità vengono utilizzate per la transazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="7f6ee-120">Selezionare **Nessuna** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="7f6ee-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-121">Click **OK**.</span></span>
10. <span data-ttu-id="7f6ee-122">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-122">Click **Edit**.</span></span>
11. <span data-ttu-id="7f6ee-123">Nel campo **Gruppo di modelli di articoli** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="7f6ee-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="7f6ee-125">I gruppi di modelli di articoli contengono impostazioni che determinano la modalità in cui gli articoli vengono controllati e gestiti all'entrata e all'uscita.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="7f6ee-126">Determinano inoltre in che modo viene calcolato il consumo di articoli.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="7f6ee-127">Selezionare **FIFO** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="7f6ee-128">Espandere la sezione **Gestisci costi**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="7f6ee-129">Nel campo **Gruppo di articoli** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="7f6ee-130">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="7f6ee-131">I gruppi di articoli vengono utilizzati per la gestione delle scorte mediante la divisione degli articoli di magazzino in gruppi.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="7f6ee-132">Selezionare **CarAudio** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="7f6ee-133">Nel Riquadro azioni selezionare **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="7f6ee-134">Selezionare **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="7f6ee-135">Nel campo **Tipo di ordine predefinito** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="7f6ee-136">Selezionare **Produzione** per specificare che l'opzione di rifornimento predefinita per la rappresentazione generale prodotto è di produrla.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="7f6ee-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-137">Select **Save**.</span></span>
20. <span data-ttu-id="7f6ee-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-138">Close the page.</span></span>
21. <span data-ttu-id="7f6ee-139">Chiudere il modulo **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-139">Close the **Released product details** form.</span></span>

