---
title: Calcolare una DBA utilizzando una struttura a più livelli (febbraio 2016)
description: In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione multilivello basata sulla scheda di determinazione costi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcc1248d64145c10f1c67bfac49c053e99dc1598
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "323366"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a><span data-ttu-id="f2ebc-103">Calcolare una DBA utilizzando una struttura a più livelli (febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="f2ebc-103">Calculate a BOM by using a multilevel structure (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f2ebc-104">In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione multilivello basata sulla scheda di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="f2ebc-105">Corrisponde alla settima attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="f2ebc-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="f2ebc-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f2ebc-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f2ebc-109">Selezionare la BOM_1 del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="f2ebc-110">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="f2ebc-111">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-111">Click Item price.</span></span>
5. <span data-ttu-id="f2ebc-112">Fare clic su Calcola costo articolo.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="f2ebc-113">Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="f2ebc-114">Nel campo Versione determinazione costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="f2ebc-115">Selezionare Versione determinazione costi 20 perché il tipo Costo pianificato e Modalità esplosione è Multilivello.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="f2ebc-116">La modalità di esplosione Multilivello è per i costi pianificati e le simulazioni.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="f2ebc-117">Non viene utilizzata per i costi standard.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="f2ebc-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-118">Click OK.</span></span>
8. <span data-ttu-id="f2ebc-119">Fare clic su Visualizza dettagli calcolo.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-119">Click View calculation details.</span></span>
    * <span data-ttu-id="f2ebc-120">Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="f2ebc-121">In questo caso, si noti come BOM_2 è stato calcolata considerando le materie prime, il processo e i costi generali con un totale di 29,40 anziché il costo standard di 10 che è stato attivato nella guida attività iniziale nella serie.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="f2ebc-122">Fare clic sulla Scheda di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="f2ebc-123">Passando alla Scheda di determinazione costi, i totali per gruppo di costi sono diversi rispetto al calcolo effettuato nella guida attività precedente.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="f2ebc-124">Nel campo Livello selezionare 'Multiplo'.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="f2ebc-125">Quando si seleziona Multiplo, i costi vengono classificati in base alla composizione di BOM_2, dove 10 deriva dal gruppo di costi M1 (ITEM_C) e 15,60 deriva dalla fabbricazione dove il gruppo di costi è L2.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="f2ebc-126">Anche i costi indiretti variano.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="f2ebc-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-127">Close the page.</span></span>
12. <span data-ttu-id="f2ebc-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f2ebc-128">Close the page.</span></span>

