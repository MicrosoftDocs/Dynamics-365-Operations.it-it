---
title: Impostare gli scadenzari pagamenti con allocazione TDS
description: Questo argomento descrive come impostare scadenziari pagamenti con l'allocazione TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023366"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="de350-103">Impostare gli scadenzari pagamenti con allocazione TDS</span><span class="sxs-lookup"><span data-stu-id="de350-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de350-104">Questo argomento descrive come impostare scadenziari pagamenti con l'allocazione TDS.</span><span class="sxs-lookup"><span data-stu-id="de350-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="de350-105">Vai a **Contabilità fornitori \> Impostazione pagamenti \> Scadenziari pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="de350-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="de350-106">[![Pagina Scadenzari pagamenti](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="de350-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="de350-107">Nel riquadro azioni, seleziona **Nuovo** per creare uno scadenziario pagamenti e immettere i dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="de350-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="de350-108">Nel campo **Allocazione** seleziona il metodo da utilizzare per allocare il pagamento per lo scadenziario pagamenti:</span><span class="sxs-lookup"><span data-stu-id="de350-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="de350-109">Totale</span><span class="sxs-lookup"><span data-stu-id="de350-109">Total</span></span>
    - <span data-ttu-id="de350-110">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="de350-110">Fixed amount</span></span>
    - <span data-ttu-id="de350-111">Quantità fissa</span><span class="sxs-lookup"><span data-stu-id="de350-111">Fixed quantity</span></span>
    - <span data-ttu-id="de350-112">Specificato</span><span class="sxs-lookup"><span data-stu-id="de350-112">Specified</span></span>

    <span data-ttu-id="de350-113">Il campo **Allocazione ritenuta d'acconto** mostra il metodo di allocazione della TDS per lo scadenziario pagamenti.</span><span class="sxs-lookup"><span data-stu-id="de350-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="de350-114">Se selezioni **Totale** nel campo **Allocazione**, il campo **Allocazione ritenuta d'acconto** viene impostato automaticamente impostato su **Totale**.</span><span class="sxs-lookup"><span data-stu-id="de350-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="de350-115">Se selezioni **Importo fisso**, **Quantità fissa** o **Specificato** nel campo **Allocazione**, il campo **Allocazione ritenuta d'acconto** viene impostato automaticamente su **In maniera proporzionale**.</span><span class="sxs-lookup"><span data-stu-id="de350-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de350-116">Se il campo **Allocazione ritenuta d'acconto** è impostato su **Totale**, le rate di pagamento sono calcolate in base all'importo lordo, che include l'importo TDS.</span><span class="sxs-lookup"><span data-stu-id="de350-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="de350-117">Se il campo **Allocazione ritenuta d'acconto** è impostato su **In maniera proporzionale**, le rate di pagamento sono calcolate in base all'importo fattura netto dopo la detrazione dell'importo TDS.</span><span class="sxs-lookup"><span data-stu-id="de350-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="de350-118">Immetti gli altri dettagli necessari e chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="de350-118">Enter the other required details, and then close the page.</span></span>
