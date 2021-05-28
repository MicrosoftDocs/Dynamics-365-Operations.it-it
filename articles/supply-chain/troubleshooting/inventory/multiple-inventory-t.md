---
title: Molteplici transazioni di magazzino per numeri batch quando l'opzione All'aggiornamento fisico è disabilitata
description: Molteplici transazioni di magazzino vengono create dopo aver rettificato una riga ordine fornitore di articoli in cui l'opzione All'aggiornamento fisico del gruppo di numeri batch è impostata su No.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026657"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="9cc89-103">Molteplici transazioni di magazzino per numeri batch quando l'opzione All'aggiornamento fisico è disabilitata</span><span class="sxs-lookup"><span data-stu-id="9cc89-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="9cc89-104">Numero KB: 4613390</span><span class="sxs-lookup"><span data-stu-id="9cc89-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="9cc89-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="9cc89-105">Symptoms</span></span>

<span data-ttu-id="9cc89-106">Molteplici transazioni di magazzino vengono create dopo aver rettificato una riga di ordine fornitore di articoli in cui l'opzione **All'aggiornamento fisico** del gruppo di numeri batch è impostata su *No*.</span><span class="sxs-lookup"><span data-stu-id="9cc89-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="9cc89-107">Quando crei un articolo in cui l'opzione **All'aggiornamento fisico** del gruppo di numeri batch è impostata su *No*, il sistema crea automaticamente un nuovo numero batch se modifichi la quantità di una riga di acquisto e salvi la pagina dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="9cc89-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="9cc89-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="9cc89-108">Resolution</span></span>

<span data-ttu-id="9cc89-109">L'impostazione **All'aggiornamento fisico** per i gruppi di numeri batch funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="9cc89-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="9cc89-110">Quando l'opzione è impostata su *Sì*, i nuovi numeri batch vengono creati solo dopo un aggiornamento fisico (ad esempio, quando gli articoli vengono spediti o ricevuti).</span><span class="sxs-lookup"><span data-stu-id="9cc89-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="9cc89-111">Quando l'opzione è impostata su *No*, viene creato un nuovo numero batch ogni volta che si verifica un aggiornamento applicabile (ad esempio, quando una nuova quantità viene aggiunta a un ordine fornitore).</span><span class="sxs-lookup"><span data-stu-id="9cc89-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
