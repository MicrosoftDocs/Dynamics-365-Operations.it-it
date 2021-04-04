---
title: Il contrassegno scorte con l'ottimizzazione della pianificazione
description: Questo argomento fornisce informazioni sulle opzioni disponibili per contrassegnare le scorte in ordini consolidati quando si utilizza l'ottimizzazione della pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7813f570afb0260e6740507c9504320c3e87be93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263352"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="bfe2d-103">Il contrassegno scorte con l'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="bfe2d-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bfe2d-104">Questo argomento fornisce informazioni sulle opzioni disponibili per contrassegnare le scorte in ordini consolidati quando si utilizza l'ottimizzazione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="bfe2d-105">*Contrassegno* viene utilizzato per collegare domanda e offerta.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="bfe2d-106">Assomiglia al *pegging*, che indica come la pianificazione generale prevede di coprire la domanda.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="bfe2d-107">Da un punto di vista della pianificazione, la differenza principale è che il contrassegno è più permanente del pegging.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="bfe2d-108">Il contrassegno è stata introdotto per supportare scenari di determinazione dei costi speciali per first in, first out (FIFO) e last in, first out (LIFO).</span><span class="sxs-lookup"><span data-stu-id="bfe2d-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="bfe2d-109">Tuttavia, ora viene utilizzato anche per alcuni scenari senza costi.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="bfe2d-110">Il contrassegno tra domanda e offerta è facoltativo e quasi permanente.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="bfe2d-111">Il contrassegno può essere rimosso manualmente da un utente oppure può essere rimosso eseguendo un'esplosione di riga dell'ordine cliente in cui l'opzione **Rimuovi contrassegno** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="bfe2d-112">Il pegging è controllato dalla pianificazione generale durante la copertura per collegare la domanda con la fornitura richiesta.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="bfe2d-113">Il pegging può essere aggiornato per ogni esecuzione della pianificazione per ottimizzare l'offerta necessaria per coprire la domanda.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="bfe2d-114">Quando la pianificazione generale aggiorna le informazioni sul pegging, rispetta qualsiasi contrassegno esistente.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="bfe2d-115">Il pegging inizia includendo il contrassegno pertinente, le prenotazioni disponibili e le prenotazioni su ordine, nella seguente sequenza:</span><span class="sxs-lookup"><span data-stu-id="bfe2d-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="bfe2d-116">Contrassegno tra domanda e offerta</span><span class="sxs-lookup"><span data-stu-id="bfe2d-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="bfe2d-117">Prenotazioni delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="bfe2d-117">On-hand reservations</span></span>
1. <span data-ttu-id="bfe2d-118">Prenotazione su ordine</span><span class="sxs-lookup"><span data-stu-id="bfe2d-118">On-order reservations</span></span>

<span data-ttu-id="bfe2d-119">Quando si stabilisce un ordine pianificato, la finestra di dialogo **Stabilizzazione** fornisce un campo **Aggiorna contrassegno** che può essere utilizzato per impostare le opzioni di contrassegno per gli ordini creati durante la stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="bfe2d-120">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="bfe2d-120">Select one of the following values:</span></span>

- <span data-ttu-id="bfe2d-121">**No** - Non viene applicato alcun contrassegno di inventario.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="bfe2d-122">**Standard** – Il contrassegno scorte viene aggiornato in base al pegging.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="bfe2d-123">Un ordine di richiesta (domanda) viene contrassegnato in base a un ordine di evasione (offerta).</span><span class="sxs-lookup"><span data-stu-id="bfe2d-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="bfe2d-124">Se una certa quantità rimane nell'ordine di evasione, non viene contrassegnata e le informazioni di riferimento vengono lasciate vuote.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="bfe2d-125">Ad esempio, se un ordine cliente per 100 pezzi è ancorato a un ordine fornitore per 150 pezzi, le informazioni di riferimento verranno assegnate solo all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="bfe2d-126">**Esteso** – Verranno contrassegnati sia l'ordine di richiesta (domanda) che l'ordine di evasione (offerta), indipendentemente dalla quantità eventualmente rimasta nell'ordine di evasione.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="bfe2d-127">Ad esempio, se un ordine cliente per 100 pezzi è ancorato a un ordine fornitore per 150 pezzi, le informazioni di riferimento verranno assegnate all'ordine cliente e all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]