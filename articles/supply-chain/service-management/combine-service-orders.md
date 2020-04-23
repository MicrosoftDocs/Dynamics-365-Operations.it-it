---
title: Combina ordini di assistenza
description: È possibile combinare ordini di assistenza
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2a27e0476ba0b4868d713d87248941dfc3579ff
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202907"
---
# <a name="combine-service-orders"></a><span data-ttu-id="74d10-103">Combina ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="74d10-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="74d10-104">Quando si creano automaticamente le righe dell'ordine di assistenza nel modulo **Contratti di assistenza**, è possibile scegliere una delle opzioni seguenti per specificare la modalità di raggruppamento desiderata:</span><span class="sxs-lookup"><span data-stu-id="74d10-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="74d10-105">**In base al contratto di assistenza**</span><span class="sxs-lookup"><span data-stu-id="74d10-105">**By service agreement**</span></span>

  - <span data-ttu-id="74d10-106">**In base all'attività di assistenza**</span><span class="sxs-lookup"><span data-stu-id="74d10-106">**By service task**</span></span>

  - <span data-ttu-id="74d10-107">**In base al dipendente**</span><span class="sxs-lookup"><span data-stu-id="74d10-107">**By employee**</span></span>

  - <span data-ttu-id="74d10-108">**In base all'oggetto assistenza**</span><span class="sxs-lookup"><span data-stu-id="74d10-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="74d10-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="74d10-109">Example</span></span>

<span data-ttu-id="74d10-110">Viene creato un contratto di assistenza con data di inizio il 31/03/2007.</span><span class="sxs-lookup"><span data-stu-id="74d10-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="74d10-111">Nel campo **Combina ordini di assistenza** specificare **In base all'oggetto assistenza**.</span><span class="sxs-lookup"><span data-stu-id="74d10-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="74d10-112">Vengono quindi create le seguenti righe del contratto di assistenza:</span><span class="sxs-lookup"><span data-stu-id="74d10-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="74d10-113">Numero riga contratto</span><span class="sxs-lookup"><span data-stu-id="74d10-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="74d10-114">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="74d10-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="74d10-115">descrizione</span><span class="sxs-lookup"><span data-stu-id="74d10-115">Description</span></span></p></th>
<th><p><span data-ttu-id="74d10-116">Intervallo</span><span class="sxs-lookup"><span data-stu-id="74d10-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="74d10-117">Oggetto assistenza</span><span class="sxs-lookup"><span data-stu-id="74d10-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="74d10-118">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="74d10-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74d10-119">1</span><span class="sxs-lookup"><span data-stu-id="74d10-119">1</span></span></p></td>
<td><p><span data-ttu-id="74d10-120"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="74d10-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="74d10-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="74d10-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="74d10-122">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="74d10-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="74d10-123">X-1</span><span class="sxs-lookup"><span data-stu-id="74d10-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="74d10-124">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="74d10-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d10-125">2</span><span class="sxs-lookup"><span data-stu-id="74d10-125">2</span></span></p></td>
<td><p><span data-ttu-id="74d10-126"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="74d10-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="74d10-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="74d10-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="74d10-128">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="74d10-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="74d10-129">X-2</span><span class="sxs-lookup"><span data-stu-id="74d10-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="74d10-130">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="74d10-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d10-131">3</span><span class="sxs-lookup"><span data-stu-id="74d10-131">3</span></span></p></td>
<td><p><span data-ttu-id="74d10-132"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="74d10-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="74d10-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="74d10-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="74d10-134">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="74d10-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="74d10-135">X-2</span><span class="sxs-lookup"><span data-stu-id="74d10-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="74d10-136">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="74d10-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74d10-137">Non viene specificato alcun intervallo di tempo per le righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="74d10-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="74d10-138">Di conseguenza, le righe degli ordini di assistenza non verranno spostate dal giorno calcolato in cui cadono.</span><span class="sxs-lookup"><span data-stu-id="74d10-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="74d10-139">Vengono quindi generate le righe degli ordini di assistenza per il periodo compreso tra il 01/04/2007 e il 30/04/2007 mediante il modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="74d10-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="74d10-140">Vengono creati complessivamente 10 ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="74d10-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="74d10-141">Poiché l'impostazione selezionata per la combinazione degli ordini di assistenza è **In base all'oggetto assistenza**, per tutti gli ordini di assistenza creati sono presenti solo righe con un oggetto assistenza specifico.</span><span class="sxs-lookup"><span data-stu-id="74d10-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="74d10-142">Le righe degli ordini di assistenza generate in base al contratto di assistenza e con la stessa data di assistenza e lo stesso oggetto vengono combinate in un unico ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="74d10-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="74d10-143">In questo esempio il calendario specificato nel modulo <STRONG>Parametri di gestione assistenza</STRONG> non prevede giorni di chiusura.</span><span class="sxs-lookup"><span data-stu-id="74d10-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="74d10-144">Ulteriori raggruppamenti delle righe negli ordini di assistenza vengono eseguiti in base agli intervalli di tempo specificati nelle righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="74d10-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="74d10-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d10-145">See also</span></span>

[<span data-ttu-id="74d10-146">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="74d10-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  


