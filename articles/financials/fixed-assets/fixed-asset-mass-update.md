---
title: Aggiornamento di massa dei cespiti
description: Se si utilizzano libri, è possibile modificare le convenzioni di ammortamento per i gruppi di cespiti appartenenti allo stesso libro.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30b9aaaabcac09c9147c350422924a23f785c0ce
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840411"
---
# <a name="fixed-asset-mass-update"></a><span data-ttu-id="30ec4-103">Aggiornamento di massa dei cespiti</span><span class="sxs-lookup"><span data-stu-id="30ec4-103">Fixed asset mass update</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30ec4-104">Se si utilizzano libri, è possibile modificare le convenzioni di ammortamento per i gruppi di cespiti appartenenti allo stesso libro.</span><span class="sxs-lookup"><span data-stu-id="30ec4-104">If you use books, you can change the depreciation conventions for groups of assets that are part of the same book.</span></span>

<span data-ttu-id="30ec4-105">Se la società ha sede, ad esempio, negli Stati Uniti ed è stato messo in servizio oltre il 40 percento dei cespiti nel quarto trimestre dell'anno, sarà necessario utilizzare la convenzione di ammortamento a metà trimestre.</span><span class="sxs-lookup"><span data-stu-id="30ec4-105">For example, if you are in the United States, and you put more than 40 percent of your assets in service during the fourth quarter of the year, you must use the mid-quarter depreciation convention.</span></span> <span data-ttu-id="30ec4-106">Per modificare tutti i cespiti che richiedono la nuova convenzione di ammortamento, sarà possibile utilizzare il processo di aggiornamento di massa.</span><span class="sxs-lookup"><span data-stu-id="30ec4-106">You can use the process for a mass update to change all assets that require the new depreciation convention.</span></span> 

<span data-ttu-id="30ec4-107">Quando si aggiorna la convenzione di ammortamento per i cespiti, si eliminano tutte le transazioni di ammortamento esistenti per i cespiti.</span><span class="sxs-lookup"><span data-stu-id="30ec4-107">When you update the depreciation convention for assets, you delete all depreciation transactions that exist for those assets.</span></span> <span data-ttu-id="30ec4-108">Si eliminano inoltre tutte le transazioni per le rettifiche di ammortamento, le transazioni di ammortamento aggiuntivo e le transazioni di ammortamento straordinario per i cespiti.</span><span class="sxs-lookup"><span data-stu-id="30ec4-108">You also delete all transactions for depreciation adjustments, transactions for bonus depreciation, and transactions for extraordinary depreciation for those assets.</span></span> 

<span data-ttu-id="30ec4-109">Per aggiornare la convenzione di ammortamento per i cespiti già dismessi, è necessario eliminare prima le transazioni di dismissione esistenti.</span><span class="sxs-lookup"><span data-stu-id="30ec4-109">To update the depreciation convention for assets that have already been disposed of, you must first delete the existing disposal transactions.</span></span> <span data-ttu-id="30ec4-110">È inoltre necessario eliminare tutte le transazioni generate a causa del processo di dismissione.</span><span class="sxs-lookup"><span data-stu-id="30ec4-110">You must also delete all transactions that were generated because of the disposal process.</span></span> 

<span data-ttu-id="30ec4-111">Dopo aver aggiornato la convenzione di ammortamento per i cespiti, è possibile elaborare l'ammortamento e l'ammortamento straordinario per ciascun cespite.</span><span class="sxs-lookup"><span data-stu-id="30ec4-111">After you update the depreciation convention for assets, you can process depreciation and extraordinary depreciation for each asset.</span></span> <span data-ttu-id="30ec4-112">È inoltre possibile apportare rettifiche manuali di ammortamento, se necessarie.</span><span class="sxs-lookup"><span data-stu-id="30ec4-112">You can also make manual depreciation adjustments, if any adjustments are required.</span></span>





