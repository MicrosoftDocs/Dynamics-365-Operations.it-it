---
title: Il numero di formula selezionato non è approvato per un ordine batch
description: Quando tenti di stabilizzare un ordine pianificato, viene visualizzato un messaggio di errore che indica che il numero di formula selezionato non è approvato per un ordine batch.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294106"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="be943-103">Il numero di formula selezionato non è approvato per un ordine batch</span><span class="sxs-lookup"><span data-stu-id="be943-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="be943-104">Codice errore: PRO2614</span><span class="sxs-lookup"><span data-stu-id="be943-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="be943-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="be943-105">Symptoms</span></span>

<span data-ttu-id="be943-106">Quando tenti di stabilizzare un ordine pianificato viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="be943-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="be943-107">Il numero formula selezionato non è approvato per un ordine batch.</span><span class="sxs-lookup"><span data-stu-id="be943-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="be943-108">Causa</span><span class="sxs-lookup"><span data-stu-id="be943-108">Cause</span></span>

<span data-ttu-id="be943-109">Il sistema convalida l'operazione di stabilizzazione per assicurarsi che sia disponibile una formula approvata per l'articolo attivo.</span><span class="sxs-lookup"><span data-stu-id="be943-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="be943-110">Probabilmente devi approvare la formula.</span><span class="sxs-lookup"><span data-stu-id="be943-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="be943-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="be943-111">Resolution</span></span>

<span data-ttu-id="be943-112">Per approvare una formula, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="be943-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="be943-113">Vai a **Gestione informazioni sul prodotto \> Distinte base e formule \> Formule**.</span><span class="sxs-lookup"><span data-stu-id="be943-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="be943-114">Seleziona la formula rilevante.</span><span class="sxs-lookup"><span data-stu-id="be943-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="be943-115">Nel riquadro azioni, nella scheda **Formula**, nel gruppo **Gestisci**, seleziona **Approva formula**.</span><span class="sxs-lookup"><span data-stu-id="be943-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="be943-116">Nella finestra di dialogo **Approva DBA o formula** seleziona un approvatore, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="be943-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
