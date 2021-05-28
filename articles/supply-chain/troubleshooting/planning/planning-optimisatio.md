---
title: Un ordine fornitore pianificato viene creato quando esiste un acquisto entro giorni negativi
description: Se il codice di copertura è Min/Max, Ottimizzazione pianificazione crea un ordine fornitore pianificato quando esiste un acquisto entro giorni negativi.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026649"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="0589f-103">Un ordine fornitore pianificato viene creato quando esiste un acquisto entro giorni negativi</span><span class="sxs-lookup"><span data-stu-id="0589f-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="0589f-104">Numero KB: 4614298</span><span class="sxs-lookup"><span data-stu-id="0589f-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="0589f-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0589f-105">Symptoms</span></span>

<span data-ttu-id="0589f-106">Se il codice di copertura è *Min/Max*, Ottimizzazione pianificazione crea un ordine fornitore pianificato quando esiste un acquisto entro giorni negativi.</span><span class="sxs-lookup"><span data-stu-id="0589f-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="0589f-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="0589f-107">Resolution</span></span>

<span data-ttu-id="0589f-108">Ottimizzazione pianificazione non supporta i giorni negativi.</span><span class="sxs-lookup"><span data-stu-id="0589f-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="0589f-109">Tuttavia, garantisce sempre che gli ordini pianificati non vengano pianificati entro il lead time relativo alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="0589f-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="0589f-110">Ad esempio, il lead time di acquisto è di 10 giorni e un ordine fornitore dovrebbe arrivare otto giorni dopo la data odierna.</span><span class="sxs-lookup"><span data-stu-id="0589f-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="0589f-111">In questo caso, l'ordine fornitore verrà utilizzato come offerta per la domanda che è di cinque giorni dalla data corrente.</span><span class="sxs-lookup"><span data-stu-id="0589f-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="0589f-112">Pertanto, ti consigliamo di modificare i lead time per coprire tutti (o quasi tutti) gli scenari.</span><span class="sxs-lookup"><span data-stu-id="0589f-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
