---
title: Calcolare una DBA utilizzando una struttura a livello singolo (febbraio 2016)
description: In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione a livello singolo basata sulla scheda di determinazione costi.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c370c623c29f2b2f3b65ffbd65aabbc941be3cb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239472"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="bd18a-103">Calcolare una DBA utilizzando una struttura a livello singolo (febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="bd18a-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd18a-104">In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione a livello singolo basata sulla scheda di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="bd18a-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="bd18a-105">Corrisponde alla sesta attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="bd18a-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="bd18a-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="bd18a-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="bd18a-107">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="bd18a-107">Go to Released products.</span></span>
2. <span data-ttu-id="bd18a-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="bd18a-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bd18a-109">Selezionare la BOM_1 del prodotto.</span><span class="sxs-lookup"><span data-stu-id="bd18a-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="bd18a-110">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="bd18a-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="bd18a-111">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="bd18a-111">Click Item price.</span></span>
5. <span data-ttu-id="bd18a-112">Fare clic su Calcola costo articolo.</span><span class="sxs-lookup"><span data-stu-id="bd18a-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="bd18a-113">Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.</span><span class="sxs-lookup"><span data-stu-id="bd18a-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="bd18a-114">Nel campo Versione determinazione costi fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bd18a-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bd18a-115">Per questa dimostrazione, selezionare 10.</span><span class="sxs-lookup"><span data-stu-id="bd18a-115">For this demo, select 10.</span></span> <span data-ttu-id="bd18a-116">Si tratta della versione di determinazione costi utilizzata per l'aggiunta del prezzo di costo ai componenti.</span><span class="sxs-lookup"><span data-stu-id="bd18a-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="bd18a-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bd18a-117">Click OK.</span></span>
8. <span data-ttu-id="bd18a-118">Fare clic su Visualizza dettagli calcolo.</span><span class="sxs-lookup"><span data-stu-id="bd18a-118">Click View calculation details.</span></span>
    * <span data-ttu-id="bd18a-119">Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.</span><span class="sxs-lookup"><span data-stu-id="bd18a-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="bd18a-120">La composizione del costo è come segue:  \*    10 è derivato da ITEM_A, 10 da ITEM_B 10, 10 da BOM_2.</span><span class="sxs-lookup"><span data-stu-id="bd18a-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="bd18a-121">In questo caso non sono presenti dettagli per BOM_2 perché è stato immesso come costo standard di 10 ma non è stato calcolato.</span><span class="sxs-lookup"><span data-stu-id="bd18a-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="bd18a-122">\*    7 è derivato dal tempo di attrezzaggio, ovvero un costo costante e il 7 aggiuntivo è derivato dall'operazione del tempo di esecuzione (processo).</span><span class="sxs-lookup"><span data-stu-id="bd18a-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="bd18a-123">\*    Sono previsti anche altri importi corrispondenti ai costi indiretti.</span><span class="sxs-lookup"><span data-stu-id="bd18a-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="bd18a-124">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="bd18a-124">@SysTaskRecorder:_RequestClose</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]