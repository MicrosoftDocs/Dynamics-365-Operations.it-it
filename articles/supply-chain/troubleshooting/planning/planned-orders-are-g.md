---
title: La pianificazione generale genera ordini pianificati per prodotti fittizi
description: L'esecuzione della pianificazione generale genera ordini pianificati per prodotti fittizi.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026650"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="5d257-103">La pianificazione generale genera ordini pianificati per prodotti fittizi</span><span class="sxs-lookup"><span data-stu-id="5d257-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="5d257-104">Numero KB: 4614729</span><span class="sxs-lookup"><span data-stu-id="5d257-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="5d257-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="5d257-105">Symptoms</span></span>

<span data-ttu-id="5d257-106">L'esecuzione della pianificazione generale genera ordini pianificati per prodotti fittizi.</span><span class="sxs-lookup"><span data-stu-id="5d257-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="5d257-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="5d257-107">Resolution</span></span>

<span data-ttu-id="5d257-108">L'impostazione dell'opzione **Fittizio** per prodotti rilasciati determina il tipo di riga predefinito nella distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="5d257-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="5d257-109">Quando l'opzione **Fittizio** è impostata su *Sì*, il sistema creerà comunque ordini pianificati per l'articolo, ma l'opzione **Fabbisogno direttamente derivato** di ogni ordine pianificato sarà impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="5d257-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="5d257-110">Pertanto, l'ordine di produzione pianificato non può essere stabilizzato da solo.</span><span class="sxs-lookup"><span data-stu-id="5d257-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="5d257-111">Al contrario, verrà sempre incluso automaticamente quando viene stabilizzato l'ordine di produzione padre.</span><span class="sxs-lookup"><span data-stu-id="5d257-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="5d257-112">Inoltre, le righe della distinta base dell'ordine fittizio pianificato verranno incluse nella distinta base dell'ordine di produzione padre.</span><span class="sxs-lookup"><span data-stu-id="5d257-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
