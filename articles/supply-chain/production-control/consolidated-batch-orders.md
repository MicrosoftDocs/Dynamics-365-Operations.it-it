---
title: Ordini batch consolidati
description: Questo articolo descrive il concetto degli ordini batch consolidati.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e8b017455c0821d97f9039d4ebf00d2dfa28eaa
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211649"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="2a857-103">Ordini batch consolidati</span><span class="sxs-lookup"><span data-stu-id="2a857-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a857-104">Questo articolo descrive il concetto degli ordini batch consolidati.</span><span class="sxs-lookup"><span data-stu-id="2a857-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="2a857-105">Un articolo in blocco che viene prodotto viene considerato un elemento padre, mentre un articolo imballato viene considerato un articolo figlio.</span><span class="sxs-lookup"><span data-stu-id="2a857-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="2a857-106">La relazione tra l'articolo in blocco e l'articolo imballato viene espressa in una conversione articolo in blocco.</span><span class="sxs-lookup"><span data-stu-id="2a857-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="2a857-107">La conversione articolo in blocco è definita nell'articolo in blocco stesso.</span><span class="sxs-lookup"><span data-stu-id="2a857-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="2a857-108">Gli articoli imballati possono essere confezionati in contenitori di uno o più formati che vengono considerati come un'unità.</span><span class="sxs-lookup"><span data-stu-id="2a857-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="2a857-109">Quando vengono consolidati gli ordini per un articolo in blocco, è possibile vedere tutti gli ordini batch correlati in un'unica visualizzazione, agevolando così l'individuazione dell'eventuale lavoro rimanente da completare.</span><span class="sxs-lookup"><span data-stu-id="2a857-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="2a857-110">Un ordine lotto consolidato può contenere qualsiasi combinazione dei seguenti ordini:</span><span class="sxs-lookup"><span data-stu-id="2a857-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="2a857-111">Un singolo ordine stoccaggio e più ordini articoli imballati</span><span class="sxs-lookup"><span data-stu-id="2a857-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="2a857-112">Più ordini stoccaggio e più ordini articoli imballati</span><span class="sxs-lookup"><span data-stu-id="2a857-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="2a857-113">Più ordini stoccaggio e un singolo ordine articoli imballati</span><span class="sxs-lookup"><span data-stu-id="2a857-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="2a857-114">Solo ordini articoli imballati</span><span class="sxs-lookup"><span data-stu-id="2a857-114">Only packed orders</span></span>




