---
title: Tenere traccia del costo medio corrente per dimensione inventariale
description: A ogni articolo di magazzino è assegnato un gruppo di dimensioni inventariali. Pertanto, il prezzo di costo medio corrente di un articolo viene quindi calcolato sulla base della selezione di dimensioni inventariali di cui viene tenuta traccia da un punto di vista finanziario.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5773e169067d5904994741f550c0d0c620f588cf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005454"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="21b4c-104">Tenere traccia del costo medio corrente per dimensione inventariale</span><span class="sxs-lookup"><span data-stu-id="21b4c-104">Track running average cost per inventory dimension</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21b4c-105">A ogni articolo di magazzino è assegnato un gruppo di dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="21b4c-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="21b4c-106">Pertanto, il prezzo di costo medio corrente di un articolo viene quindi calcolato sulla base della selezione di dimensioni inventariali di cui viene tenuta traccia da un punto di vista finanziario.</span><span class="sxs-lookup"><span data-stu-id="21b4c-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="21b4c-107">Sono disponibili tre tipi di dimensioni inventariali: prodotto, immagazzinamento e tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="21b4c-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="21b4c-108">Le dimensioni prodotto includono la configurazione, le dimensioni e il colore</span><span class="sxs-lookup"><span data-stu-id="21b4c-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="21b4c-109">e ne viene sempre tenuta traccia finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="21b4c-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="21b4c-110">Le dimensioni di tracciabilità e di immagazzinamento includono il sito, il magazzino, la posizione, lo stato inventario, la targa, il numero batch e il numero di serie</span><span class="sxs-lookup"><span data-stu-id="21b4c-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="21b4c-111">L'utente può scegliere di quali di esse tenere traccia finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="21b4c-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="21b4c-112">**Esempio 1**</span><span class="sxs-lookup"><span data-stu-id="21b4c-112">**Example 1**</span></span> 

<span data-ttu-id="21b4c-113">Se del gruppo di dimensione di immagazzinamento associato all'articolo viene tenuta traccia finanziariamente per magazzino, il prezzo di costo medio corrente verrà calcolato per ogni magazzino.</span><span class="sxs-lookup"><span data-stu-id="21b4c-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="21b4c-114">Sono stati fatturati i seguenti ordini fornitore:</span><span class="sxs-lookup"><span data-stu-id="21b4c-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="21b4c-115">È stato fatturato un ordine acquisto per una quantità 2 a un prezzo di costo di 10,00 EUR per il magazzino GW.</span><span class="sxs-lookup"><span data-stu-id="21b4c-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="21b4c-116">È stato fatturato un ordine acquisto per una quantità 3 a un prezzo di costo di 12,00 EUR per il magazzino GW.</span><span class="sxs-lookup"><span data-stu-id="21b4c-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="21b4c-117">È stato fatturato un ordine acquisto per una quantità 5 a un prezzo di costo di 15,00 EUR per il magazzino MW.</span><span class="sxs-lookup"><span data-stu-id="21b4c-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="21b4c-118">Il prezzo di costo medio corrente per il magazzino GW è EUR 11,20 e il prezzo di costo medio corrente per il magazzino MW è 15,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="21b4c-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="21b4c-119">Se viene registrata una fattura ordine cliente per il magazzino GW,</span><span class="sxs-lookup"><span data-stu-id="21b4c-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="21b4c-120">il valore delle scorte e il costo del venduto (prima della chiusura dell'inventario senza contrassegni) è di 11,20 EUR.</span><span class="sxs-lookup"><span data-stu-id="21b4c-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="21b4c-121">Se viene registrato un altro ordine cliente per il magazzino MW,</span><span class="sxs-lookup"><span data-stu-id="21b4c-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="21b4c-122">il valore delle scorte e il costo del venduto (prima della chiusura dell'inventario senza contrassegni) è di 15,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="21b4c-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="21b4c-123">**Esempio 2** Se del gruppo di dimensioni di immagazzinamento collegato all'articolo viene tenuta traccia finanziariamente dal magazzino e del gruppo di dimensioni di tracciabilità viene tenuta traccia finanziariamente per numero batch, il prezzo di costo medio corrente verrà calcolato per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="21b4c-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="21b4c-124">**Nota:** è consigliabile visualizzare sempre il prezzo di costo con tutte le dimensioni finanziarie di cui viene tenuta traccia.</span><span class="sxs-lookup"><span data-stu-id="21b4c-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="21b4c-125">Sono stati fatturati i seguenti ordini fornitore:</span><span class="sxs-lookup"><span data-stu-id="21b4c-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="21b4c-126">È stato fatturato un ordine fornitore per una quantità 2 a un prezzo di costo di 10,00 EUR per il magazzino GW e il batch AAA.</span><span class="sxs-lookup"><span data-stu-id="21b4c-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="21b4c-127">È stato fatturato un ordine fornitore per una quantità 3 a un prezzo di costo di 12,00 EUR per il magazzino GW e il batch AAA.</span><span class="sxs-lookup"><span data-stu-id="21b4c-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="21b4c-128">È stato fatturato un ordine fornitore per una quantità 2 a un prezzo di costo di 15,00 EUR per il magazzino GW e il batch BBB.</span><span class="sxs-lookup"><span data-stu-id="21b4c-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="21b4c-129">Il prezzo di costo medio corrente per il magazzino GW e il batch AAA è EUR 11,20 e il prezzo di costo medio corrente per il magazzino GW e il batch BBB è 15,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="21b4c-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>



