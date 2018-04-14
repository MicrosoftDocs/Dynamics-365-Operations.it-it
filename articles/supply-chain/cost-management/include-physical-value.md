---
title: Includi valore fisico
description: Si utilizza la casella di controllo Includi valore fisico nella scheda dettaglio Modello inventariale della pagina Gruppi di modelli di articolo per specificare se nel calcolo del prezzo di costo medio corrente dell'articolo vengono considerate le transazioni aggiornate fisicamente.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 03d5823d721c9abde4af0ac4203fdfc48f02ac47
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="include-physical-value"></a><span data-ttu-id="825a8-103">Includi valore fisico</span><span class="sxs-lookup"><span data-stu-id="825a8-103">Include physical value</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="825a8-104">Si utilizza la casella di controllo Includi valore fisico nella scheda dettaglio Modello inventariale della pagina Gruppi di modelli di articolo per specificare se nel calcolo del prezzo di costo medio corrente dell'articolo vengono considerate le transazioni aggiornate fisicamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="825a8-105">La casella di controllo **Includi valore fisico** ha i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="825a8-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="825a8-106">Valore</span><span class="sxs-lookup"><span data-stu-id="825a8-106">Value</span></span>    | <span data-ttu-id="825a8-107">Risultato</span><span class="sxs-lookup"><span data-stu-id="825a8-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="825a8-108">Selezionata</span><span class="sxs-lookup"><span data-stu-id="825a8-108">Selected</span></span> | <span data-ttu-id="825a8-109">Per calcolare il prezzo di costo medio corrente verranno utilizzate sia le transazioni aggiornate fisicamente sia le transazioni aggiornate finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="825a8-110">Deselezionata</span><span class="sxs-lookup"><span data-stu-id="825a8-110">Cleared</span></span>  | <span data-ttu-id="825a8-111">Per calcolare il prezzo di costo medio corrente verranno utilizzate solo le transazioni aggiornate finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="825a8-112">La casella di controllo ha effetti leggermente diversi a seconda del modello inventariale in uso.</span><span class="sxs-lookup"><span data-stu-id="825a8-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="825a8-113">Se si seleziona la casella di controllo **Includi valore fisico** quando si utilizza il modello inventariale FIFO (First in, first out), LIFO (Last in, first out) o Data LIFO, con la chiusura dell'inventario verranno apportate rettifiche anche alle transazioni aggiornate fisicamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="825a8-114">Se non si seleziona la casella di controllo **Includi valore fisico** con questi modelli inventariali, con la chiusura dell'inventario verranno eseguite compensazioni solo per le transazioni aggiornate finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="825a8-115">Se si utilizzano i modelli inventariali media ponderata o data media ponderata, la chiusura inventario determinerà la compensazione solo delle transazioni aggiornate finanziariamente, indipendentemente dalla selezione della casella di controllo **Includi valore fisico**.</span><span class="sxs-lookup"><span data-stu-id="825a8-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="825a8-116">**Esempio 1** È stata selezionata la casella di controllo**Includi valore fisico** e sono stati ricevuti i seguenti ordini fornitore:</span><span class="sxs-lookup"><span data-stu-id="825a8-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="825a8-117">È stato fatturato un ordine acquisto per una quantità 2 a un prezzo di costo di 10,00 EUR aggiornato nel documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="825a8-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated</span></span>
-   <span data-ttu-id="825a8-118">Un ordine acquisto per una quantità 3 a un prezzo di costo di 12,00 EUR aggiornato nella fattura</span><span class="sxs-lookup"><span data-stu-id="825a8-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated</span></span>

<span data-ttu-id="825a8-119">In questo caso il prezzo di costo medio corrente sarà di 11,20 EUR, poiché per calcolare il prezzo di costo verranno utilizzate sia le transazioni aggiornate fisicamente sia le transazioni aggiornate finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-119">In this case, the running average cost price will be USD 11.20, because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> <span data-ttu-id="825a8-120">**Esempio 2** Non è stata selezionata la casella di controllo **Includi valore fisico** e il prezzo di costo nell'impostazione dell'articolo è di 10,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="825a8-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> <span data-ttu-id="825a8-121">È stato ricevuto un ordine acquisto per una quantità 20 a un prezzo di costo di 12,00 EUR aggiornato nel documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="825a8-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span> <span data-ttu-id="825a8-122">Quando viene registrato un ordine cliente, viene registrato automaticamente un importo costi di 10,00 EUR, poiché il prezzo di costo medio corrente non includerà transazioni registrate fisicamente.</span><span class="sxs-lookup"><span data-stu-id="825a8-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> <span data-ttu-id="825a8-123">**Nota:** a fini di confronto, se si seleziona la casella di controllo **Includi valore fisico** per questo articolo, quando si registra un ordine cliente, l'importo costi registrato sarà 12,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="825a8-123">**Note:** For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>




