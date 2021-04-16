---
title: Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata
description: Questo argomento procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.
author: ShylaThompson
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c41e9e3267f72a2452eddfeb15f8f5cba79b0b98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820156"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="84480-103">Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata</span><span class="sxs-lookup"><span data-stu-id="84480-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="84480-104">Questo argomento procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="84480-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="84480-105">Questa è la terza procedura di otto che illustra come sviluppare le combinazioni per la configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="84480-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="84480-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="84480-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="84480-107">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="84480-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="84480-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="84480-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="84480-109">Selezionare la rappresentazione generale prodotto che è stata rilasciata nella seconda procedura.</span><span class="sxs-lookup"><span data-stu-id="84480-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="84480-110">La rappresentazione generale prodotto viene creata con la tecnologia di configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="84480-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="84480-111">Nel riquadro azioni fare clic su **Prodotto**.</span><span class="sxs-lookup"><span data-stu-id="84480-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="84480-112">Fare clic su **Gruppi di dimensioni** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84480-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="84480-113">Nel campo **Gruppo di dimensioni di immagazzinamento** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="84480-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="84480-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="84480-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="84480-115">Il gruppo dimensione di immagazzinamento determina quali dimensioni di immagazzinamento vengono utilizzate per la transazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="84480-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="84480-116">Selezionare **Sito** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="84480-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="84480-117">Nel campo **Gruppo di dimensioni di tracciabilità** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="84480-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="84480-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="84480-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="84480-119">Il gruppo dimensione di tracciabilità determina quali dimensioni di tracciabilità vengono utilizzate per la transazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="84480-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="84480-120">Selezionare **Nessuna** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="84480-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="84480-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84480-121">Click **OK**.</span></span>
10. <span data-ttu-id="84480-122">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84480-122">Click **Edit**.</span></span>
11. <span data-ttu-id="84480-123">Nel campo **Gruppo di modelli di articoli** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="84480-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="84480-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="84480-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="84480-125">I gruppi di modelli di articoli contengono impostazioni che determinano la modalità in cui gli articoli vengono controllati e gestiti all'entrata e all'uscita.</span><span class="sxs-lookup"><span data-stu-id="84480-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="84480-126">Determinano inoltre in che modo viene calcolato il consumo di articoli.</span><span class="sxs-lookup"><span data-stu-id="84480-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="84480-127">Selezionare **FIFO** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="84480-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="84480-128">Espandere la sezione **Gestisci costi**.</span><span class="sxs-lookup"><span data-stu-id="84480-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="84480-129">Nel campo **Gruppo di articoli** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="84480-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="84480-130">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="84480-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="84480-131">I gruppi di articoli vengono utilizzati per la gestione delle scorte mediante la divisione degli articoli di magazzino in gruppi.</span><span class="sxs-lookup"><span data-stu-id="84480-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="84480-132">Selezionare **CarAudio** per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="84480-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="84480-133">Nel Riquadro azioni selezionare **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="84480-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="84480-134">Selezionare **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="84480-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="84480-135">Nel campo **Tipo di ordine predefinito** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="84480-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="84480-136">Selezionare **Produzione** per specificare che l'opzione di rifornimento predefinita per la rappresentazione generale prodotto è di produrla.</span><span class="sxs-lookup"><span data-stu-id="84480-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="84480-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84480-137">Select **Save**.</span></span>
20. <span data-ttu-id="84480-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84480-138">Close the page.</span></span>
21. <span data-ttu-id="84480-139">Chiudere il modulo **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="84480-139">Close the **Released product details** form.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]