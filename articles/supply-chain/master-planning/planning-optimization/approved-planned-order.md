---
title: Approva ordini pianificati
description: Questo argomento descrive l'approvazione degli ordini pianificati supportati in Ottimizzazione pianificazione.
author: ChristianRytt
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 6c215a89403f16336caae5c62cde6df469c4091c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825893"
---
# <a name="approve-planned-orders"></a><span data-ttu-id="c9c08-103">Approva ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="c9c08-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c9c08-104">Questo argomento fornisce informazioni su come aggiornare lo stato degli ordini pianificati in Ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c9c08-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="c9c08-105">L'approvazione degli ordini pianificati è un passaggio facoltativo, nel percorso per creare un ordine stabilizzato da un ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="c9c08-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="c9c08-106">Si consiglia di approvare gli ordini pianificati modificati, altrimenti le modifiche verranno ignorate e sovrascritte dalla successiva esecuzione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c9c08-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Flusso dell'ordine pianificato](media/approved-planned-orders-1.png)

<span data-ttu-id="c9c08-108">Il campo **Stato** aiuta a tracciare l'avanzamento utilizzando i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="c9c08-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="c9c08-109">**Inevaso:** Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di *Inevaso*.</span><span class="sxs-lookup"><span data-stu-id="c9c08-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="c9c08-110">Gli ordini pianificati con questo stato verranno eliminati durante la successiva esecuzione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c9c08-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="c9c08-111">**Completato:** se si decide di non stabilizzare un ordine pianificato, è possibile modificare lo stato in *Completato* per indicare che la valutazione di questo ordine pianificato è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c9c08-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="c9c08-112">Notare che gli stati *Inevaso* e *Completato* sono trattati allo stesso modo dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c9c08-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="c9c08-113">**Approvato:** se si desidera mantenere le modifiche o si prevede di confermare un ordine pianificato, modificare lo stato in *Approvato*.</span><span class="sxs-lookup"><span data-stu-id="c9c08-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="c9c08-114">Gli ordini pianificati con stato *Approvato* vengono considerati come fornitura fissa e prevista dalla pianificazione generale, non vengono modificati né eliminati durante le esecuzioni di pianificazione generale successive.</span><span class="sxs-lookup"><span data-stu-id="c9c08-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="c9c08-115">Per raggiungere questo obiettivo, la logica di pianificazione copia gli ordini pianificati con stato *Approvato* dalla vecchia versione del piano alla nuova versione del piano durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="c9c08-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="c9c08-116">Notare che gli ordini pianificati *approvati* sono considerati fornitura solo all'interno del piano generale specifico.</span><span class="sxs-lookup"><span data-stu-id="c9c08-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="c9c08-117">È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**.</span><span class="sxs-lookup"><span data-stu-id="c9c08-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]