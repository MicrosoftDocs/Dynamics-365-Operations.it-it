---
title: Il cumulo degli sconti cliente non riesce quando vengono utilizzati gruppi di sconti articolo
description: Quando utilizzi accordi sugli sconti cliente in combinazione con gruppi di sconti articolo, gli sconti vengono calcolati, ma il cumulo non riesce.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026633"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="58705-103">Il cumulo degli sconti cliente non riesce quando vengono utilizzati gruppi di sconti articolo</span><span class="sxs-lookup"><span data-stu-id="58705-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="58705-104">Numero KB: 4611372</span><span class="sxs-lookup"><span data-stu-id="58705-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="58705-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="58705-105">Symptoms</span></span>

<span data-ttu-id="58705-106">Quando utilizzi accordi sugli sconti cliente (di tipo *importo*) in combinazione con gruppi di sconti articolo, gli sconti vengono calcolati, ma il cumulo non riesce.</span><span class="sxs-lookup"><span data-stu-id="58705-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="58705-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="58705-107">Resolution</span></span>

<span data-ttu-id="58705-108">Il sistema si comporta come previsto.</span><span class="sxs-lookup"><span data-stu-id="58705-108">The system is behaving as designed.</span></span> <span data-ttu-id="58705-109">I gruppi di articoli raggruppano solo gli articoli che hanno la stessa condizione di soglia.</span><span class="sxs-lookup"><span data-stu-id="58705-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="58705-110">La condizione di sconto (soglia) viene impostata in base all'importo di ciascun articolo e non all'importo cumulato per qualsiasi articolo nel gruppo di articoli.</span><span class="sxs-lookup"><span data-stu-id="58705-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
