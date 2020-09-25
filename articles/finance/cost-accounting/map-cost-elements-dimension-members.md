---
title: Eseguire il mapping dei membri di dimensione elemento di costo a un set comune di membri di dimensione
description: Mappando membri delle dimensioni elemento di costo diversi a un set comune di membri delle dimensioni elemento di costo, si uniscono i dati in un formato comune per scopi di analisi.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 835a542ad5f7606f76805e54fda9f49ecc79205f
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759282"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="3f72f-103">Eseguire il mapping dei membri di dimensione elemento di costo a un set comune di membri di dimensione</span><span class="sxs-lookup"><span data-stu-id="3f72f-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f72f-104">Mappando membri delle dimensioni elemento di costo diversi a un set comune di membri delle dimensioni elemento di costo, si uniscono i dati in un formato comune per scopi di analisi.</span><span class="sxs-lookup"><span data-stu-id="3f72f-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="3f72f-105">Se si è una società globale conforme ai requisiti contabili statutari, è possibile che si utilizzino più piani dei conti.</span><span class="sxs-lookup"><span data-stu-id="3f72f-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="3f72f-106">Quando si importano i membri delle dimensioni elemento di costo da piani dei conti diversi, è possibile finire con una combinazione di conti.</span><span class="sxs-lookup"><span data-stu-id="3f72f-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="3f72f-107">Tuttavia, questi conti potrebbero effettivamente avere la stessa natura e può essere opportuno analizzare e allocare i relativi costi utilizzando un formato comune.</span><span class="sxs-lookup"><span data-stu-id="3f72f-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="3f72f-108">Mappare i membri delle dimensioni elemento di costo a un formato comune</span><span class="sxs-lookup"><span data-stu-id="3f72f-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="3f72f-109">Nel seguente esempio viene illustrato come un controller di costi può creare una nuova dimensione elemento di costo nella contabilità industriale che mappa i membri delle dimensioni elemento di costo dalla struttura del piano dei conti negli Stati Uniti e dalla struttura del piano dei conti francese a un set comune di membri delle dimensioni elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="3f72f-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="3f72f-110">È quindi possibile utilizzare il set comune dei membri delle dimensioni elemento di costo per analizzare i dati sui costi delle due persone giuridiche in un movimento CoGe di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="3f72f-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="3f72f-111">Origine: piano dei conti statunitense</span><span class="sxs-lookup"><span data-stu-id="3f72f-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="3f72f-112">Origine: piano dei conti francese</span><span class="sxs-lookup"><span data-stu-id="3f72f-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="3f72f-113">Nuovo set comune di membri delle dimensioni elemento di costo</span><span class="sxs-lookup"><span data-stu-id="3f72f-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="3f72f-114">Membri delle dimensioni elemento di costo importati dal piano dei conti statunitense</span><span class="sxs-lookup"><span data-stu-id="3f72f-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="3f72f-115">Membri delle dimensioni elemento di costo importati dal piano dei conti francese</span><span class="sxs-lookup"><span data-stu-id="3f72f-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="3f72f-116">Mapping dei membri delle dimensioni elemento di costo statunitensi e francesi a un set comune</span><span class="sxs-lookup"><span data-stu-id="3f72f-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="3f72f-117">5001: Vendite</span><span class="sxs-lookup"><span data-stu-id="3f72f-117">5001: Sales</span></span>                                                           | <span data-ttu-id="3f72f-118">5001: Vendite e annunci</span><span class="sxs-lookup"><span data-stu-id="3f72f-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="3f72f-119">5000: Vendite e annunci</span><span class="sxs-lookup"><span data-stu-id="3f72f-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="3f72f-120">5030: Annunci</span><span class="sxs-lookup"><span data-stu-id="3f72f-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="3f72f-121">6390: Acquisti scorte\*</span><span class="sxs-lookup"><span data-stu-id="3f72f-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="3f72f-122">7000: Spese di pulizia</span><span class="sxs-lookup"><span data-stu-id="3f72f-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="3f72f-123">7001: Spese di pulizia</span><span class="sxs-lookup"><span data-stu-id="3f72f-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="3f72f-124">7001: Spesa di viaggio</span><span class="sxs-lookup"><span data-stu-id="3f72f-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="3f72f-125">7001: Spese di viaggio</span><span class="sxs-lookup"><span data-stu-id="3f72f-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="3f72f-126">\*Il membro della dimensione elemento di costo francese Acquisto scorte non è mappato.</span><span class="sxs-lookup"><span data-stu-id="3f72f-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="3f72f-127">Conversione valutaria</span><span class="sxs-lookup"><span data-stu-id="3f72f-127">Currency conversion</span></span>
<span data-ttu-id="3f72f-128">I vari piani dei conti utilizzati possono essere impostati per l'utilizzo di valute diverse.</span><span class="sxs-lookup"><span data-stu-id="3f72f-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="3f72f-129">In questo caso, assicurarsi di specificare una conversione valutaria, in modo che i dati relativi ai costi vengano elaborati con la valuta corretta, come definito nel conto CoGe di contabilità industriale in cui i membri delle dimensioni elemento di costo vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="3f72f-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="3f72f-130">Nell'esempio precedente, se il dollaro statunitense (USD) viene utilizzato nel conto CoGe di contabilità industriale, è necessario creare una conversione valutaria da USD a EUR (euro) per elaborare le transazioni per i membri delle dimensioni elemento di costo mappati.</span><span class="sxs-lookup"><span data-stu-id="3f72f-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="3f72f-131">Aggiornare i mapping in qualsiasi momento</span><span class="sxs-lookup"><span data-stu-id="3f72f-131">Update mappings at any time</span></span>
<span data-ttu-id="3f72f-132">È possibile aggiornare in qualsiasi momento le definizioni di mapping per una dimensione elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="3f72f-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="3f72f-133">Poiché i mapping non dipendono dalle date, le modifiche vengono applicate alla successiva elaborazione delle transazioni costi o esecuzione di calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3f72f-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>



