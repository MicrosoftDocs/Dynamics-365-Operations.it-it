---
title: Ridurre l'ammortamento a saldi decrescenti dopo una divisione
description: In questo argomento viene descritto il metodo utilizzato in Cespiti per calcolare l'ammortamento dopo la divisione di un cespite utilizzando il metodo di riduzione del saldo.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 615d17c71b904d426081d4c57492ba7e95c2c749
ms.sourcegitcommit: 65f9e2584c0530b1a71655aae09101691726b47f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "4650669"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="f7e32-103">Ridurre l'ammortamento a saldi decrescenti dopo una divisione</span><span class="sxs-lookup"><span data-stu-id="f7e32-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7e32-104">In questo argomento viene descritto il metodo utilizzato in Cespiti per calcolare l'ammortamento dopo la divisione di un cespite in un altro cespite utilizzando il metodo di riduzione del saldo.</span><span class="sxs-lookup"><span data-stu-id="f7e32-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="f7e32-105">L'anno di ammortamento configurato nel libro cespiti è l'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="f7e32-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="f7e32-106">Per ulteriori informazioni, vedi [Ridurre l'ammortamento del saldo](reduce-balance-depreciation.md) e [Dividere un cespite](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="f7e32-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="f7e32-107">Se dividi un cespite durante un periodo fiscale successivo al periodo in cui il cespite è stato acquisito, l'ammortamento del saldo ridotto contabilizzerà il valore contabile netto del cespite dell'anno precedente.</span><span class="sxs-lookup"><span data-stu-id="f7e32-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="f7e32-108">Conterrà anche le transazioni di acquisizione e di rettifica dell'ammortamento generate dalla transazione che ha suddiviso il bene.</span><span class="sxs-lookup"><span data-stu-id="f7e32-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="f7e32-109">Questo comportamento presuppone che il cespite sia stato acquisito in un anno fiscale e diviso in un anno fiscale successivo.</span><span class="sxs-lookup"><span data-stu-id="f7e32-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="f7e32-110">L'importo che deve essere ammortizzato per il cespite originale dopo la suddivisione riflette l'NBV del cespite prima che il cespite fosse diviso e la transazione di rettifica dell'acquisizione e dell'ammortamento registrata per la divisione.</span><span class="sxs-lookup"><span data-stu-id="f7e32-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="f7e32-111">Ad esempio, sono in vigore le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="f7e32-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="f7e32-112">Il periodo fiscale va dal 30 giugno al 1 luglio.</span><span class="sxs-lookup"><span data-stu-id="f7e32-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="f7e32-113">La percentuale di saldo decrescente è del 18% e un cespite 'viene acquistato a giugno 2019 a un prezzo di acquisto di $10.000.</span><span class="sxs-lookup"><span data-stu-id="f7e32-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="f7e32-114">L'ammortamento del primo anno fiscale è pari a $18.000, l'ammortamento mensile è pari a $150 e il cespite viene quindi ammortizzato fino a novembre 2019, per un importo di $738,75.</span><span class="sxs-lookup"><span data-stu-id="f7e32-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="f7e32-115">A novembre 2019, l'80% del cespite viene diviso in un altro cespite.</span><span class="sxs-lookup"><span data-stu-id="f7e32-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="f7e32-116">[![Ridurre l'ammortamento a saldi decrescenti dopo una divisione](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="f7e32-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="f7e32-117">L'importo da ammortizzare per il cespite originale è $1.822,25.</span><span class="sxs-lookup"><span data-stu-id="f7e32-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="f7e32-118">Questo importo è uguale al valore contabile netto prima della registrazione della transazione di divisione ($ 9.111,25), più la rettifica di acquisizione generata durante la registrazione della transazione di divisione (- $ 8.000), più la rettifica di ammortamento generata durante la transazione di divisione ($ 711).</span><span class="sxs-lookup"><span data-stu-id="f7e32-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="f7e32-119">Pertanto, l'ammortamento per il secondo anno è (1.822,25 × 18 percento) ÷ 12 = $27,33.</span><span class="sxs-lookup"><span data-stu-id="f7e32-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="f7e32-120">L'importo da ammortizzare per il nuovo cespite nel primo anno è (8.000 × 18 percento) ÷ 12 = $120.</span><span class="sxs-lookup"><span data-stu-id="f7e32-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>
