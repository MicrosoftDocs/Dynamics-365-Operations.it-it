--- 
title: Ricevere articoli in un ordine fornitore da una richiesta articolo
description: In questa procedura viene illustrato come ricevere gli articoli in un ordine fornitore da una richiesta articolo.
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7c9093439c4c0c4645d96ad97ba56f31026ec334
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="50c40-103">Ricevere articoli in un ordine fornitore da una richiesta articolo</span><span class="sxs-lookup"><span data-stu-id="50c40-103">Receive items on purchase order from item requirement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50c40-104">In questa procedura viene illustrato come ricevere gli articoli in un ordine fornitore da una richiesta articolo.</span><span class="sxs-lookup"><span data-stu-id="50c40-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="50c40-105">Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="50c40-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="50c40-106">Questa attività utilizza il set di dati dimostrativi USSI.</span><span class="sxs-lookup"><span data-stu-id="50c40-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="50c40-107">Passare a Gestione progetti e contabilità > Progetti > Tutti i progetti.</span><span class="sxs-lookup"><span data-stu-id="50c40-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="50c40-108">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="50c40-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="50c40-109">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="50c40-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="50c40-110">Fare clic su Richieste articoli.</span><span class="sxs-lookup"><span data-stu-id="50c40-110">Click Item requirements.</span></span>
5. <span data-ttu-id="50c40-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="50c40-111">Click New.</span></span>
6. <span data-ttu-id="50c40-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="50c40-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="50c40-113">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="50c40-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="50c40-114">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="50c40-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="50c40-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="50c40-115">Click Save.</span></span>
10. <span data-ttu-id="50c40-116">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="50c40-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="50c40-117">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="50c40-117">Click Functions.</span></span>
12. <span data-ttu-id="50c40-118">Fare clic su Crea ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="50c40-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="50c40-119">Selezionare la casella di controllo Includi.</span><span class="sxs-lookup"><span data-stu-id="50c40-119">Select the Include check box.</span></span>
14. <span data-ttu-id="50c40-120">Nel campo Conto fornitore, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="50c40-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="50c40-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="50c40-121">Click OK.</span></span>
16. <span data-ttu-id="50c40-122">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="50c40-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="50c40-123">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="50c40-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="50c40-124">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="50c40-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="50c40-125">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="50c40-125">Click Confirm.</span></span>
20. <span data-ttu-id="50c40-126">Nel riquadro azioni fare clic su Ricevimento.</span><span class="sxs-lookup"><span data-stu-id="50c40-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="50c40-127">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="50c40-127">Click Product receipt.</span></span>
22. <span data-ttu-id="50c40-128">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="50c40-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="50c40-129">Digitare un valore nel campo Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="50c40-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="50c40-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="50c40-130">Click OK.</span></span>

