---
title: Convenzioni del leasing di cespiti
description: In questo argomento vengono descritte le convenzioni per i cespiti in leasing.
author: moaamer
manager: Ann Beebe
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7072c34ccbffc6bf135f55fd594cac4d9ea5a463
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237518"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="cc289-103">Convenzioni del leasing di cespiti</span><span class="sxs-lookup"><span data-stu-id="cc289-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cc289-104">In questo argomento vengono descritte le convenzioni per i cespiti in leasing.</span><span class="sxs-lookup"><span data-stu-id="cc289-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="cc289-105">Le convenzioni di leasing sono utilizzate per determinare la data di inizio di un libro di leasing.</span><span class="sxs-lookup"><span data-stu-id="cc289-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="cc289-106">Se la convenzione di leasing è impostata su **Nessuna**, la data di inizio è uguale alla data di inizio del leasing (ovvero, il valore del campo **Data di inizio leasing**).</span><span class="sxs-lookup"><span data-stu-id="cc289-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="cc289-107">Se la convenzione di leasing è impostata su **Mese intero**, la data di inizio è il primo giorno del mese in cui cade la data di inizio del leasing.</span><span class="sxs-lookup"><span data-stu-id="cc289-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="cc289-108">La data di inizio determina la data di inizio del periodo per i piani di ammortamento delle passività e dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="cc289-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="cc289-109">Gli interessi passivi e le spese di ammortamento sono registrati alla data di fine periodo delle programmazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cc289-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="cc289-110">La rilevazione iniziale e la registrazione contabile di rettifica vengono registrate alla data di inizio.</span><span class="sxs-lookup"><span data-stu-id="cc289-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="cc289-111">La funzionalità per le convenzioni di leasing deve essere attivata tramite Feature Management.</span><span class="sxs-lookup"><span data-stu-id="cc289-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="cc289-112">Nell'area di lavoro **Gestione delle funzionalità** trova e seleziona la funzione denominata **Convenzione di leasing per leasing di cespiti** quindi seleziona **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="cc289-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="cc289-113">Le convenzioni di leasing sono assegnate all'impostazione di un libro cespiti di leasing.</span><span class="sxs-lookup"><span data-stu-id="cc289-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="cc289-114">Per visualizzare o assegnare la convenzione di leasing, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="cc289-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="cc289-115">Vai a **Leasing cespiti \> Imposta \> Libri di leasing**.</span><span class="sxs-lookup"><span data-stu-id="cc289-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="cc289-116">Nel campo **Convenzione di leasing**, seleziona uno dei seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="cc289-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="cc289-117">Convenzione di leasing</span><span class="sxs-lookup"><span data-stu-id="cc289-117">Leasing convention</span></span> | <span data-ttu-id="cc289-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc289-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="cc289-119">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="cc289-119">None</span></span>               | <span data-ttu-id="cc289-120">I piani di ammortamento delle passività e dei cespiti iniziano alla data di inizio del leasing, poiché la data di inizio è uguale alla data di inizio del leasing.</span><span class="sxs-lookup"><span data-stu-id="cc289-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="cc289-121">La data di fine è un mese dopo.</span><span class="sxs-lookup"><span data-stu-id="cc289-121">The end date is one month later.</span></span> <span data-ttu-id="cc289-122">Questa convenzione di leasing non garantisce che gli interessi verranno registrati l'ultimo giorno di ogni mese.</span><span class="sxs-lookup"><span data-stu-id="cc289-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="cc289-123">Mese intero</span><span class="sxs-lookup"><span data-stu-id="cc289-123">Full month</span></span>         | <span data-ttu-id="cc289-124">Per i leasing che hanno una data di inizio che cade in qualsiasi momento del mese, i piani di ammortamento delle passività e dei cespiti iniziano a maturare le spese il primo giorno di quel mese.</span><span class="sxs-lookup"><span data-stu-id="cc289-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="cc289-125">Questa convenzione di leasing garantisce che gli interessi maturino l'ultimo giorno di ogni mese per l'intero mese.</span><span class="sxs-lookup"><span data-stu-id="cc289-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="cc289-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cc289-126">Select **Save**.</span></span>

<span data-ttu-id="cc289-127">Quando viene creato un leasing, la data di inizio di ciascun libro viene inserita automaticamente in base alla data di inizio immessa per il leasing e alla convenzione di leasing specificata per il libro.</span><span class="sxs-lookup"><span data-stu-id="cc289-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]