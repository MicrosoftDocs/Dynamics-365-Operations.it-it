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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7bd3ac8cf3c025b082b33247fcd020aebc010bc8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247720"
---
# <a name="combine-service-orders"></a><span data-ttu-id="172ec-103">Combina ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="172ec-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="172ec-104">Quando si creano automaticamente le righe dell'ordine di assistenza nel modulo **Contratti di assistenza**, è possibile scegliere una delle opzioni seguenti per specificare la modalità di raggruppamento desiderata:</span><span class="sxs-lookup"><span data-stu-id="172ec-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="172ec-105">**In base al contratto di assistenza**</span><span class="sxs-lookup"><span data-stu-id="172ec-105">**By service agreement**</span></span>

  - <span data-ttu-id="172ec-106">**In base all'attività di assistenza**</span><span class="sxs-lookup"><span data-stu-id="172ec-106">**By service task**</span></span>

  - <span data-ttu-id="172ec-107">**In base al dipendente**</span><span class="sxs-lookup"><span data-stu-id="172ec-107">**By employee**</span></span>

  - <span data-ttu-id="172ec-108">**In base all'oggetto assistenza**</span><span class="sxs-lookup"><span data-stu-id="172ec-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="172ec-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="172ec-109">Example</span></span>

<span data-ttu-id="172ec-110">Viene creato un contratto di assistenza con data di inizio il 31/03/2007.</span><span class="sxs-lookup"><span data-stu-id="172ec-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="172ec-111">Nel campo **Combina ordini di assistenza** specificare **In base all'oggetto assistenza**.</span><span class="sxs-lookup"><span data-stu-id="172ec-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="172ec-112">Vengono quindi create le seguenti righe del contratto di assistenza:</span><span class="sxs-lookup"><span data-stu-id="172ec-112">You then create the following service agreement lines:</span></span>

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
<th><p><span data-ttu-id="172ec-113">Numero riga contratto</span><span class="sxs-lookup"><span data-stu-id="172ec-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="172ec-114">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="172ec-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="172ec-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="172ec-115">Description</span></span></p></th>
<th><p><span data-ttu-id="172ec-116">Intervallo</span><span class="sxs-lookup"><span data-stu-id="172ec-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="172ec-117">Oggetto assistenza</span><span class="sxs-lookup"><span data-stu-id="172ec-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="172ec-118">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="172ec-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="172ec-119">1</span><span class="sxs-lookup"><span data-stu-id="172ec-119">1</span></span></p></td>
<td><p><span data-ttu-id="172ec-120"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="172ec-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="172ec-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="172ec-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="172ec-122">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="172ec-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="172ec-123">X-1</span><span class="sxs-lookup"><span data-stu-id="172ec-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="172ec-124">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="172ec-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="172ec-125">2</span><span class="sxs-lookup"><span data-stu-id="172ec-125">2</span></span></p></td>
<td><p><span data-ttu-id="172ec-126"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="172ec-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="172ec-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="172ec-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="172ec-128">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="172ec-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="172ec-129">X-2</span><span class="sxs-lookup"><span data-stu-id="172ec-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="172ec-130">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="172ec-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="172ec-131">3</span><span class="sxs-lookup"><span data-stu-id="172ec-131">3</span></span></p></td>
<td><p><span data-ttu-id="172ec-132"><strong>Ore</strong></span><span class="sxs-lookup"><span data-stu-id="172ec-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="172ec-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="172ec-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="172ec-134">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="172ec-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="172ec-135">X-2</span><span class="sxs-lookup"><span data-stu-id="172ec-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="172ec-136">01/04/2007</span><span class="sxs-lookup"><span data-stu-id="172ec-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="172ec-137">Non viene specificato alcun intervallo di tempo per le righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="172ec-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="172ec-138">Di conseguenza, le righe degli ordini di assistenza non verranno spostate dal giorno calcolato in cui cadono.</span><span class="sxs-lookup"><span data-stu-id="172ec-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="172ec-139">Vengono quindi generate le righe degli ordini di assistenza per il periodo compreso tra il 01/04/2007 e il 30/04/2007 mediante il modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="172ec-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="172ec-140">Vengono creati complessivamente 10 ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="172ec-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="172ec-141">Poiché l'impostazione selezionata per la combinazione degli ordini di assistenza è **In base all'oggetto assistenza**, per tutti gli ordini di assistenza creati sono presenti solo righe con un oggetto assistenza specifico.</span><span class="sxs-lookup"><span data-stu-id="172ec-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="172ec-142">Le righe degli ordini di assistenza generate in base al contratto di assistenza e con la stessa data di assistenza e lo stesso oggetto vengono combinate in un unico ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="172ec-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="172ec-143">In questo esempio il calendario specificato nel modulo <STRONG>Parametri di gestione assistenza</STRONG> non prevede giorni di chiusura.</span><span class="sxs-lookup"><span data-stu-id="172ec-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="172ec-144">Ulteriori raggruppamenti delle righe negli ordini di assistenza vengono eseguiti in base agli intervalli di tempo specificati nelle righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="172ec-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="172ec-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172ec-145">See also</span></span>

[<span data-ttu-id="172ec-146">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="172ec-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]