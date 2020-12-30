---
title: Dismettere un cespito come scarto
description: Questo argomento descrive il processo di eliminazione delle transazioni per un cespite dismesso come scarto.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444723"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="dd885-103">Dismettere un cespito come scarto</span><span class="sxs-lookup"><span data-stu-id="dd885-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd885-104">Questo argomento descrive il processo di eliminazione delle transazioni per un cespite dismesso come scarto.</span><span class="sxs-lookup"><span data-stu-id="dd885-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="dd885-105">I tipi di transazioni che possono essere eliminati includono le transazioni di acquisizione e di ammortamento accumulato di un cespite e altre transazioni relativi ai cespiti.</span><span class="sxs-lookup"><span data-stu-id="dd885-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="dd885-106">L'eliminazione di queste transazioni altera i conti dello stato patrimoniale, ad esempio conti di rettifica acquisizione, rettifica ammortamento, rivalutazione e svalutazione.</span><span class="sxs-lookup"><span data-stu-id="dd885-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="dd885-107">Transazione</span><span class="sxs-lookup"><span data-stu-id="dd885-107">Transaction</span></span>                                         | <span data-ttu-id="dd885-108">Dare (dr.)</span><span class="sxs-lookup"><span data-stu-id="dd885-108">Debit (Dr.)</span></span> | <span data-ttu-id="dd885-109">Avere (cr.)</span><span class="sxs-lookup"><span data-stu-id="dd885-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="dd885-110">Ammortamento accumulato dr.</span><span class="sxs-lookup"><span data-stu-id="dd885-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="dd885-111">X</span><span class="sxs-lookup"><span data-stu-id="dd885-111">X</span></span>           |              |
| <span data-ttu-id="dd885-112">Profitti/perdite cespiti cr.</span><span class="sxs-lookup"><span data-stu-id="dd885-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="dd885-113">X</span><span class="sxs-lookup"><span data-stu-id="dd885-113">X</span></span>            |
| <span data-ttu-id="dd885-114">Profitti/perdite cespiti dr.</span><span class="sxs-lookup"><span data-stu-id="dd885-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="dd885-115">X</span><span class="sxs-lookup"><span data-stu-id="dd885-115">X</span></span>           |              |
| <span data-ttu-id="dd885-116">Conti di acquisizione cespiti cr.</span><span class="sxs-lookup"><span data-stu-id="dd885-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="dd885-117">X</span><span class="sxs-lookup"><span data-stu-id="dd885-117">X</span></span>            |
| <span data-ttu-id="dd885-118">Profitti/perdite cespiti dr. (valore contabile \[netto\])</span><span class="sxs-lookup"><span data-stu-id="dd885-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="dd885-119">X</span><span class="sxs-lookup"><span data-stu-id="dd885-119">X</span></span>           |              |
| <span data-ttu-id="dd885-120">Profitti/perdite cespiti cr. (valore contabile netto)</span><span class="sxs-lookup"><span data-stu-id="dd885-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="dd885-121">X</span><span class="sxs-lookup"><span data-stu-id="dd885-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="dd885-122">Si consiglia di cooperare strettamente con il responsabile o il supervisore finanziario della società per identificare i conti corretti da utilizzare per ogni tipo di transazione nonché verificare che il processo di dismissione e le transazioni che genera aggiornino correttamente quei conti.</span><span class="sxs-lookup"><span data-stu-id="dd885-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="dd885-123">Prima di dismettere un cespite come scarto, è necessario creare conti CoGe associati a valore di acquisizione, ammortamento per l'anno corrente, ammortamento per gli anni precedenti e valore contabile netto del cespite.</span><span class="sxs-lookup"><span data-stu-id="dd885-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="dd885-124">I tipi di transazione cespiti sono elencati nella pagina **Profili di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="dd885-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="dd885-125">Selezionare **Cespiti \> Impostazione \> Profili registrazione cespiti**, quindi nella Scheda dettaglio **Dismissione**, selezionare **Scarto** nel campo sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="dd885-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="dd885-126">Nell'illustrazione seguente viene visualizzato l'elenco dei tipi di transazione cespiti nella pagina **Profili registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="dd885-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="dd885-127">[![Dismissione di un cespite come scarto, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="dd885-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="dd885-128">Per l'esempio seguente, un cespite è stato acquisito il 1° gennaio 2018 e verrà scartato il 31 marzo 2019.</span><span class="sxs-lookup"><span data-stu-id="dd885-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="dd885-129">**Prezzo di acquisizione:** 24.000 dollari USA (USD)</span><span class="sxs-lookup"><span data-stu-id="dd885-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="dd885-130">**Vita utile:** due anni</span><span class="sxs-lookup"><span data-stu-id="dd885-130">**Service life:** Two years</span></span>
- <span data-ttu-id="dd885-131">**Metodo di ammortamento:** Vita utile a quote costanti</span><span class="sxs-lookup"><span data-stu-id="dd885-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="dd885-132">**Importo di ammortamento:** 1.000 USD per mese</span><span class="sxs-lookup"><span data-stu-id="dd885-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="dd885-133">Il valore contabile netto di un cespite viene calcolato utilizzando la seguente formula:</span><span class="sxs-lookup"><span data-stu-id="dd885-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="dd885-134">Valore contabile netto = Prezzo di acquisizione - Ammortamento</span><span class="sxs-lookup"><span data-stu-id="dd885-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="dd885-135">In questo esempio, il cespite è stato acquisito e ammortizzato per 15 mesi, dal gennaio 2018 al marzo 2019.</span><span class="sxs-lookup"><span data-stu-id="dd885-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="dd885-136">Di conseguenza, il valore contabile netto del cespite è 9.000 USD (24.000 USD - 15.000 USD).</span><span class="sxs-lookup"><span data-stu-id="dd885-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="dd885-137">[![Esempio di ammortamento dei cespiti](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="dd885-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="dd885-138">Per creare un giornale di registrazione di dismissioni, passare a **Cespiti \> Scritture contabili \> Giornale di registrazione cespiti** e selezionare **Righe** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="dd885-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="dd885-139">Selezionare **Dismissione - scarto** e selezionare un ID cespite.</span><span class="sxs-lookup"><span data-stu-id="dd885-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="dd885-140">Per dismettere completamente il cespite, non immettere un valore nel campo **Dare** o nel campo **Avere**.</span><span class="sxs-lookup"><span data-stu-id="dd885-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="dd885-141">[![Giornale di registrazione cespiti](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="dd885-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="dd885-142">La transazione di tipo Dismissione - scarto modifica i valori per il libro cespiti nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="dd885-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="dd885-143">Nella sezione **Saldo**, il campo **Stato** diventa **Scartato**.</span><span class="sxs-lookup"><span data-stu-id="dd885-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="dd885-144">Nella sezione **Uscita**, il campo **Data di dismissione** è impostato sulla data in cui il cespite è stato scartato.</span><span class="sxs-lookup"><span data-stu-id="dd885-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="dd885-145">[![Dettaglio del giornale di registrazione cespiti](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="dd885-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="dd885-146">L'illustrazione seguente mostra il saldo cespiti.</span><span class="sxs-lookup"><span data-stu-id="dd885-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="dd885-147">[![Saldo cespiti](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="dd885-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="dd885-148">L'illustrazione seguente mostra il giustificativo registrato.</span><span class="sxs-lookup"><span data-stu-id="dd885-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="dd885-149">[![Valore contabile netto](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="dd885-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>
