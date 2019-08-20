---
title: Ordini fornitore per un progetto
description: Questo articolo descrive i vari metodi da utilizzare per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 971a4ea0abac43c160d8a6f46f385cbfc5134ffd
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838873"
---
# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="9e230-104">Ordini fornitore per un progetto</span><span class="sxs-lookup"><span data-stu-id="9e230-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e230-105">Questo articolo descrive i vari metodi da utilizzare per creare ordini fornitore per un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="9e230-106">Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="9e230-107">In Microsoft Dynamics 365 for Finance and Operations, è possibile utilizzare più metodi per creare ordini fornitore per un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-107">In Microsoft Dynamics 365 for Finance and Operations, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="9e230-108">Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="9e230-109">Metodi per la creazione di un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="9e230-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="9e230-110">Per creare un ordine fornitore nel modulo Gestione progetti e contabilità, è possibile utilizzare uno dei seguenti metodi.</span><span class="sxs-lookup"><span data-stu-id="9e230-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="9e230-111">Lo scopo dell'ordine fornitore determina quando verrà consumato l'ordine e, di conseguenza, quando gli articoli verranno addebitati a un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e230-112">Metodo</span><span class="sxs-lookup"><span data-stu-id="9e230-112">Method</span></span></th>
<th><span data-ttu-id="9e230-113">Scopo</span><span class="sxs-lookup"><span data-stu-id="9e230-113">Purpose</span></span></th>
<th><span data-ttu-id="9e230-114">Consumo articoli</span><span class="sxs-lookup"><span data-stu-id="9e230-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9e230-115">Creare un ordine fornitore direttamente da un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="9e230-116">Utilizzare questo metodo per acquistare articoli da un fornitore esterno per il consumo nell'ambito di un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="9e230-117">È possibile creare l'ordine fornitore in due modi:</span><span class="sxs-lookup"><span data-stu-id="9e230-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="9e230-118">Dal progetto stesso.</span><span class="sxs-lookup"><span data-stu-id="9e230-118">From the project itself.</span></span> <span data-ttu-id="9e230-119">In questo caso il progetto è già definito per l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="9e230-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="9e230-120">Accedendo all'ordine fornitore del progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="9e230-121">È necessario selezionare sia il fornitore sia il progetto per cui viene creato l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="9e230-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="9e230-122">Gli articoli vengono consumati quando viene aggiornata la fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="9e230-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e230-123">Creare un ordine fornitore da un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9e230-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="9e230-124">Utilizzare questo metodo per acquistare articoli quando si crea un ordine cliente da un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="9e230-125">Gli articoli vengono consumati quando l'ordine cliente viene fatturato al cliente.</span><span class="sxs-lookup"><span data-stu-id="9e230-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e230-126">Creare un ordine fornitore da una richiesta articolo.</span><span class="sxs-lookup"><span data-stu-id="9e230-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="9e230-127">Utilizzare questo metodo per acquistare articoli quando si crea una richiesta articolo da un progetto.</span><span class="sxs-lookup"><span data-stu-id="9e230-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="9e230-128">Gli articoli vengono consumati quando viene aggiornato il documento di trasporto relativo alla richiesta articolo.</span><span class="sxs-lookup"><span data-stu-id="9e230-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="9e230-129">Quando si aggiorna la fattura fornitore o il documento di trasporto, verrà chiesto di aggiornare il documento di trasporto per la richiesta articolo.</span><span class="sxs-lookup"><span data-stu-id="9e230-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="9e230-130">Per ulteriori informazioni, vedere [Ricevere articoli in un ordine fornitore da una richiesta articolo](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="9e230-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

