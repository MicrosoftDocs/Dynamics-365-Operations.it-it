---
title: Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino
description: Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026642"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="3a986-103">Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino</span><span class="sxs-lookup"><span data-stu-id="3a986-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="3a986-104">Numero KB: 4614667</span><span class="sxs-lookup"><span data-stu-id="3a986-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="3a986-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="3a986-105">Symptoms</span></span>

<span data-ttu-id="3a986-106">Molteplici intestazioni lavoro vengono create per la stessa targa di destinazione come parte di un singolo evento di ricezione dell'app di magazzino.</span><span class="sxs-lookup"><span data-stu-id="3a986-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="3a986-107">Tuttavia, solo un'etichetta della targa viene stampata al ricevimento del prodotto.</span><span class="sxs-lookup"><span data-stu-id="3a986-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="3a986-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="3a986-108">Resolution</span></span>

<span data-ttu-id="3a986-109">Il sistema si comporta come previsto.</span><span class="sxs-lookup"><span data-stu-id="3a986-109">The system is behaving as designed.</span></span>

<span data-ttu-id="3a986-110">Nella progettazione corrente, viene sempre generata una singola etichetta di targa, indipendentemente dal numero di combinazioni di intestazioni lavoro e righe lavoro esistenti.</span><span class="sxs-lookup"><span data-stu-id="3a986-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="3a986-111">L'etichetta generata include le informazioni per una sola combinazione.</span><span class="sxs-lookup"><span data-stu-id="3a986-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="3a986-112">Per risolvere questo problema, assicurati che la creazione dell'intestazione lavoro sia sempre mappata a una sola targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a986-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
