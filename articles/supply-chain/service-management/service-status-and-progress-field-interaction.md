---
title: Interazione dei campi Stato e Avanzamento relativi agli ordini di assistenza
description: "Nel modulo Ordini di assistenza il campo Avanzamento nell'intestazione dell'ordine di assistenza riflette lo stato dell'intero ordine di assistenza, mentre nel campo Stato è indicato lo stato delle singole righe dell'ordine di assistenza."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 51ef39266e8de00488954918568d00a297a9b50a
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---


# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="55b83-103">Interazione dei campi Stato e Avanzamento relativi agli ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="55b83-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="55b83-104">Nel modulo **Ordini di assistenza** il campo **Avanzamento** nell'intestazione dell'ordine di assistenza riflette lo stato dell'intero ordine di assistenza, mentre nel campo **Stato** è indicato lo stato delle singole righe dell'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="55b83-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="55b83-105">Avanzamento</span><span class="sxs-lookup"><span data-stu-id="55b83-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="55b83-106">Stato riga 1</span><span class="sxs-lookup"><span data-stu-id="55b83-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="55b83-107">Stato riga 2</span><span class="sxs-lookup"><span data-stu-id="55b83-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="55b83-108">Stato riga 3</span><span class="sxs-lookup"><span data-stu-id="55b83-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55b83-109"><strong>In corso</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-110"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-111"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-112"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55b83-113"><strong>In corso</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-114"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-115"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-116"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55b83-117"><strong>In corso</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-118"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-119"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-120"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55b83-121"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-122"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-123"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-124"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55b83-125"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-126"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-127"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-128"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55b83-129"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-130"><strong>Contabilizzato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-131"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="55b83-132"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="55b83-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55b83-133">L'avanzamento di un ordine di assistenza è In corso se in tutte le righe è presente lo stato **Creato** e anche se in alcune righe è presente lo stato **Annullato** o **Contabilizzato**.</span><span class="sxs-lookup"><span data-stu-id="55b83-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="55b83-134">Se tutte le righe in un ordine di assistenza sono contrassegnate dallo stato **Contabilizzato**, l'avanzamento dell'ordine di assistenza è **Contabilizzato**.</span><span class="sxs-lookup"><span data-stu-id="55b83-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="55b83-135">Se lo stato di alcune righe è **Contabilizzato** e di altre è **Annullato**, l'avanzamento è ancora **Contabilizzato**.</span><span class="sxs-lookup"><span data-stu-id="55b83-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  



