---
title: Elaborare le allocazioni
description: Questo articolo fornisce informazioni sulle allocazioni, le opzioni per elaborarle in Microsoft Dynamics 365 Finance e sul modo in cui possono essere utilizzate nella pianificazione del budget. Le allocazioni vengono utilizzate per distribuire importi tra più combinazioni di conti CoGe. Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all'oggetto corretto.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c8216ebdd1f26601743e6b35849be0813d06b4a
ms.sourcegitcommit: 4676ea9646fa1a182103ecab93e78a69001f0b8d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "3612664"
---
# <a name="process-allocations"></a><span data-ttu-id="ac297-105">Elaborare le allocazioni</span><span class="sxs-lookup"><span data-stu-id="ac297-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac297-106">Questo articolo fornisce informazioni sulle allocazioni, le opzioni per elaborarle e sul modo in cui possono essere utilizzate nella pianificazione del budget.</span><span class="sxs-lookup"><span data-stu-id="ac297-106">This article provides information about allocations, the options for processing them, and how they can be used in budget planning.</span></span> <span data-ttu-id="ac297-107">Le allocazioni vengono utilizzate per distribuire importi tra più combinazioni di conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="ac297-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="ac297-108">Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all'oggetto corretto.</span><span class="sxs-lookup"><span data-stu-id="ac297-108">They help ensure that expenses or revenues are charged to the correct object in accounting.</span></span>

<span data-ttu-id="ac297-109">Le seguenti funzionalità supportano questo processo:</span><span class="sxs-lookup"><span data-stu-id="ac297-109">The following capabilities support this process:</span></span>

-   <span data-ttu-id="ac297-110">Allocare manualmente gli importi delle transazioni utilizzando l'operazione Dividi nelle distribuzioni contabili o applicando i modelli predefiniti di dimensioni finanziarie a un documento.</span><span class="sxs-lookup"><span data-stu-id="ac297-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="ac297-111">Per ulteriori informazioni, vedere [Distribuzioni contabili](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="ac297-111">For more information, see [Accounting distributions](../accounts-payable/accounting-distributions.md).</span></span>
-   <span data-ttu-id="ac297-112">Allocare automaticamente gli importi delle transazioni in base ai termini di allocazione definite in un conto principale.</span><span class="sxs-lookup"><span data-stu-id="ac297-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="ac297-113">Le voci del conto di allocazione verranno generate per ciascun giornale di registrazione in base alla percentuale e al conto CoGe di destinazione ogni volta che una voce contabile soddisfa i criteri definiti come conto CoGe originale.</span><span class="sxs-lookup"><span data-stu-id="ac297-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span> <span data-ttu-id="ac297-114">Per ulteriori informazioni, vedere [Condizioni di allocazione del conto principale](../general-ledger/main-account-allocation-terms.md).</span><span class="sxs-lookup"><span data-stu-id="ac297-114">For more information, see [Main account allocation terms](../general-ledger/main-account-allocation-terms.md)</span></span>
-   <span data-ttu-id="ac297-115">Allocare automaticamente i saldi contabili o gli importi fissi in base alle regole di allocazione contabile.</span><span class="sxs-lookup"><span data-stu-id="ac297-115">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="ac297-116">Le regole di allocazione contabile vengono elaborate su base periodica utilizzando i giornali di registrazione allocazione.</span><span class="sxs-lookup"><span data-stu-id="ac297-116">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> <span data-ttu-id="ac297-117">Per ulteriori informazioni, vedere [Regole di allocazione](../general-ledger/ledger-allocation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="ac297-117">For more information, see [Allocation rules](../general-ledger/ledger-allocation-rules.md).</span></span>

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="ac297-118">Allocazioni in fase di pianificazione del budget</span><span class="sxs-lookup"><span data-stu-id="ac297-118">Allocations in budget planning</span></span>

<span data-ttu-id="ac297-119">Le regole di allocazione contabile possono essere utilizzate per il piano di budget.</span><span class="sxs-lookup"><span data-stu-id="ac297-119">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="ac297-120">Quando si utilizzano le regole di allocazione contabile nella pianificazione del budget, le regole di allocazione hanno un funzionamento analogo a quello nella contabilità generale, ma i dati di origine e i dati di destinazione provengono dal piano di budget.</span><span class="sxs-lookup"><span data-stu-id="ac297-120">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="ac297-121">È possibile selezionare manualmente le regole di allocazione contabile da utilizzare per il piano di budget.</span><span class="sxs-lookup"><span data-stu-id="ac297-121">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="ac297-122">In alternativa, è possibile utilizzare una programmazione di allocazione che viene eseguita come parte di un processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac297-122">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="ac297-123">Non è possibile utilizzare le regole di allocazione contabile interaziendali per la pianificazione del budget.</span><span class="sxs-lookup"><span data-stu-id="ac297-123">You can’t use intercompany ledger allocation rules for budget planning.</span></span>

