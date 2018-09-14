--- 
title: Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata
description: Questa procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="7857c-103">Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata</span><span class="sxs-lookup"><span data-stu-id="7857c-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7857c-104">Questa procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="7857c-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="7857c-105">Questa è la terza procedura di otto che illustra come sviluppare le combinazioni per la configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7857c-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="7857c-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="7857c-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7857c-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="7857c-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="7857c-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7857c-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7857c-109">Selezionare la rappresentazione generale prodotto che è stata rilasciata nella seconda procedura.</span><span class="sxs-lookup"><span data-stu-id="7857c-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="7857c-110">La rappresentazione generale prodotto viene creata con la tecnologia di configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7857c-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="7857c-111">Nel riquadro azioni fare clic su Prodotto.</span><span class="sxs-lookup"><span data-stu-id="7857c-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="7857c-112">Fare clic su gruppi di dimensioni per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7857c-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="7857c-113">Nel campo Gruppo di dimensioni di immagazzinamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7857c-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7857c-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7857c-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7857c-115">Il gruppo dimensione di immagazzinamento determina quali dimensioni di immagazzinamento vengono utilizzate per la transazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="7857c-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="7857c-116">Selezionare Sito per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7857c-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="7857c-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7857c-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7857c-118">Nel campo Gruppo di dimensioni di tracciabilità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7857c-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="7857c-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7857c-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7857c-120">Il gruppo dimensione di tracciabilità determina quali dimensioni di tracciabilità vengono utilizzate per la transazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="7857c-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="7857c-121">Selezionare Nessuna per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7857c-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="7857c-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7857c-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="7857c-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7857c-123">Click OK.</span></span>
12. <span data-ttu-id="7857c-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7857c-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="7857c-125">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="7857c-125">Click Edit.</span></span>
    * <span data-ttu-id="7857c-126">Aprire il modulo Dettagli prodotto rilasciato per continuare l'attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7857c-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="7857c-127">Nel campo Gruppo di modelli di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7857c-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="7857c-128">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7857c-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7857c-129">I gruppi di modelli di articoli contengono impostazioni che determinano la modalità in cui gli articoli vengono controllati e gestiti all'entrata e all'uscita.</span><span class="sxs-lookup"><span data-stu-id="7857c-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="7857c-130">Determinano inoltre in che modo viene calcolato il consumo di articoli.</span><span class="sxs-lookup"><span data-stu-id="7857c-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="7857c-131">Selezionare FIFO per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7857c-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="7857c-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7857c-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="7857c-133">Espandere o comprimere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="7857c-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="7857c-134">Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7857c-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="7857c-135">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7857c-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7857c-136">I gruppi di articoli vengono utilizzati per la gestione delle scorte mediante la divisione degli articoli di magazzino in gruppi.</span><span class="sxs-lookup"><span data-stu-id="7857c-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="7857c-137">Selezionare CarAudio per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7857c-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="7857c-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7857c-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="7857c-139">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="7857c-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="7857c-140">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="7857c-140">Click Default order settings.</span></span>
23. <span data-ttu-id="7857c-141">Nel campo Tipo di ordine predefinito selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="7857c-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="7857c-142">Selezionare Produzione per specificare che l'opzione di rifornimento predefinita per la rappresentazione generale prodotto è di produrla.</span><span class="sxs-lookup"><span data-stu-id="7857c-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="7857c-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7857c-143">Close the page.</span></span>
25. <span data-ttu-id="7857c-144">Chiudere il modulo Dettagli prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="7857c-144">Close the Released product details form.</span></span>


