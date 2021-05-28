---
title: Non è presente alcun valore di data iniziale nella scheda Prezzi attivi della pagina Prezzo articolo
description: Non è presente alcun valore di data iniziale nella scheda Prezzi attivi della pagina Prezzo articolo.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026658"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="fad72-103">Non è presente alcun valore di data iniziale nella scheda Prezzi attivi della pagina Prezzo articolo</span><span class="sxs-lookup"><span data-stu-id="fad72-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="fad72-104">Numero KB: 4613548</span><span class="sxs-lookup"><span data-stu-id="fad72-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="fad72-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="fad72-105">Symptoms</span></span>

<span data-ttu-id="fad72-106">Non è presente alcun valore di **Data iniziale** nella scheda **Prezzi attivi** della pagina **Prezzo articolo**.</span><span class="sxs-lookup"><span data-stu-id="fad72-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="fad72-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="fad72-107">Resolution</span></span>

<span data-ttu-id="fad72-108">Il valore **Data iniziale** (data di validità) impostato sul prezzo in sospeso non viene trasferito al prezzo attivo.</span><span class="sxs-lookup"><span data-stu-id="fad72-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="fad72-109">Quando un record di costo di un articolo viene immesso per la prima volta, ha uno stato *In sospeso* e una data di validità prevista.</span><span class="sxs-lookup"><span data-stu-id="fad72-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="fad72-110">Quando si attiva il record del costo dell'articolo, lo stato viene aggiornato e diventa *attivo* e la data di validità viene aggiornata alla data di attivazione.</span><span class="sxs-lookup"><span data-stu-id="fad72-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="fad72-111">Pertanto, la data di attivazione del prezzo attivo è sempre la data effettiva dell'attivazione.</span><span class="sxs-lookup"><span data-stu-id="fad72-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="fad72-112">Per ulteriori informazioni, vedi [Panoramica delle versioni di determinazione costi](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="fad72-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
