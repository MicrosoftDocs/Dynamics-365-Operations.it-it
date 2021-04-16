---
title: Combina ordini di assistenza
description: È possibile combinare ordini di assistenza
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41b4a3234e4104372f1052d89c2417984e9cd10d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840559"
---
# <a name="combine-service-orders"></a><span data-ttu-id="76a46-103">Combina ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="76a46-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="76a46-104">Quando si creano automaticamente le righe dell'ordine di assistenza nel modulo **Contratti di assistenza**, è possibile scegliere una delle opzioni seguenti per specificare la modalità di raggruppamento desiderata:</span><span class="sxs-lookup"><span data-stu-id="76a46-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="76a46-105">**In base al contratto di assistenza**</span><span class="sxs-lookup"><span data-stu-id="76a46-105">**By service agreement**</span></span>

  - <span data-ttu-id="76a46-106">**In base all'attività di assistenza**</span><span class="sxs-lookup"><span data-stu-id="76a46-106">**By service task**</span></span>

  - <span data-ttu-id="76a46-107">**In base al dipendente**</span><span class="sxs-lookup"><span data-stu-id="76a46-107">**By employee**</span></span>

  - <span data-ttu-id="76a46-108">**In base all'oggetto assistenza**</span><span class="sxs-lookup"><span data-stu-id="76a46-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="76a46-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="76a46-109">Example</span></span>

<span data-ttu-id="76a46-110">Viene creato un contratto di assistenza con data di inizio il 31/03/2007.</span><span class="sxs-lookup"><span data-stu-id="76a46-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="76a46-111">Nel campo **Combina ordini di assistenza** specificare **In base all'oggetto assistenza**.</span><span class="sxs-lookup"><span data-stu-id="76a46-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="76a46-112">Vengono quindi create le seguenti righe del contratto di assistenza:</span><span class="sxs-lookup"><span data-stu-id="76a46-112">You then create the following service agreement lines:</span></span>

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
<th><p><span data-ttu-id="76a46-113">Numero riga contratto</span><span class="sxs-lookup"><span data-stu-id="76a46-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="76a46-114">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="76a46-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="76a46-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76a46-115">Description</span></span></p></th>
<th><p><span data-ttu-id="76a46-116">Intervallo</span><span class="sxs-lookup"><span data-stu-id="76a46-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="76a46-117">Oggetto assistenza</span><span class="sxs-lookup"><span data-stu-id="76a46-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="76a46-118">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="76a46-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76a46-119">1</span><span class="sxs-lookup"><span data-stu-id="76a46-119">1</span></span></p></td>
<td><p><span data-ttu-id="76a46-120"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="76a46-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="76a46-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="76a46-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="76a46-122">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="76a46-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="76a46-123">X-1</span><span class="sxs-lookup"><span data-stu-id="76a46-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="76a46-124">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="76a46-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a46-125">2</span><span class="sxs-lookup"><span data-stu-id="76a46-125">2</span></span></p></td>
<td><p><span data-ttu-id="76a46-126"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="76a46-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="76a46-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="76a46-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="76a46-128">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="76a46-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="76a46-129">X-2</span><span class="sxs-lookup"><span data-stu-id="76a46-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="76a46-130">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="76a46-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a46-131">3</span><span class="sxs-lookup"><span data-stu-id="76a46-131">3</span></span></p></td>
<td><p><span data-ttu-id="76a46-132"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="76a46-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="76a46-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="76a46-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="76a46-134">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="76a46-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="76a46-135">X-2</span><span class="sxs-lookup"><span data-stu-id="76a46-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="76a46-136">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="76a46-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76a46-137">Non viene specificato alcun intervallo di tempo per le righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="76a46-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="76a46-138">Di conseguenza, le righe degli ordini di assistenza non verranno spostate dal giorno calcolato in cui cadono.</span><span class="sxs-lookup"><span data-stu-id="76a46-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="76a46-139">Vengono quindi generate le righe degli ordini di assistenza per il periodo compreso tra il 01/04/2007 e il 30/04/2007 mediante il modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="76a46-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="76a46-140">Vengono creati complessivamente 10 ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="76a46-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="76a46-141">Poiché l'impostazione selezionata per la combinazione degli ordini di assistenza è **In base all'oggetto assistenza**, per tutti gli ordini di assistenza creati sono presenti solo righe con un oggetto assistenza specifico.</span><span class="sxs-lookup"><span data-stu-id="76a46-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="76a46-142">Le righe degli ordini di assistenza generate in base al contratto di assistenza e con la stessa data di assistenza e lo stesso oggetto vengono combinate in un unico ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="76a46-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="76a46-143">In questo esempio il calendario specificato nel modulo <STRONG>Parametri di gestione assistenza</STRONG> non prevede giorni di chiusura.</span><span class="sxs-lookup"><span data-stu-id="76a46-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="76a46-144">Ulteriori raggruppamenti delle righe negli ordini di assistenza vengono eseguiti in base agli intervalli di tempo specificati nelle righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="76a46-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="76a46-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76a46-145">See also</span></span>

[<span data-ttu-id="76a46-146">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="76a46-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]