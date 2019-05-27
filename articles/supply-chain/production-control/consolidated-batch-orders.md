---
title: Ordini batch consolidati
description: Questo articolo descrive il concetto degli ordini batch consolidati.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49c2df19168855e6e6ab9ff061bcdce698947b20
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569453"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="05e6e-103">Ordini batch consolidati</span><span class="sxs-lookup"><span data-stu-id="05e6e-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05e6e-104">Questo articolo descrive il concetto degli ordini batch consolidati.</span><span class="sxs-lookup"><span data-stu-id="05e6e-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="05e6e-105">Un articolo in blocco che viene prodotto viene considerato un elemento padre, mentre un articolo imballato viene considerato un articolo figlio.</span><span class="sxs-lookup"><span data-stu-id="05e6e-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="05e6e-106">La relazione tra l'articolo in blocco e l'articolo imballato viene espressa in una conversione articolo in blocco.</span><span class="sxs-lookup"><span data-stu-id="05e6e-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="05e6e-107">La conversione articolo in blocco è definita nell'articolo in blocco stesso.</span><span class="sxs-lookup"><span data-stu-id="05e6e-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="05e6e-108">Gli articoli imballati possono essere confezionati in contenitori di uno o più formati che vengono considerati come un'unità.</span><span class="sxs-lookup"><span data-stu-id="05e6e-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="05e6e-109">Quando vengono consolidati gli ordini per un articolo in blocco, è possibile vedere tutti gli ordini batch correlati in un'unica visualizzazione, agevolando così l'individuazione dell'eventuale lavoro rimanente da completare.</span><span class="sxs-lookup"><span data-stu-id="05e6e-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="05e6e-110">Un ordine lotto consolidato può contenere qualsiasi combinazione dei seguenti ordini:</span><span class="sxs-lookup"><span data-stu-id="05e6e-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="05e6e-111">Un singolo ordine stoccaggio e più ordini articoli imballati</span><span class="sxs-lookup"><span data-stu-id="05e6e-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="05e6e-112">Più ordini stoccaggio e più ordini articoli imballati</span><span class="sxs-lookup"><span data-stu-id="05e6e-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="05e6e-113">Più ordini stoccaggio e un singolo ordine articoli imballati</span><span class="sxs-lookup"><span data-stu-id="05e6e-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="05e6e-114">Solo ordini articoli imballati</span><span class="sxs-lookup"><span data-stu-id="05e6e-114">Only packed orders</span></span>




