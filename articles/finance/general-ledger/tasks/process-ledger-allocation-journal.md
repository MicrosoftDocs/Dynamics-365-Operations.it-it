---
title: Elaborare giornale di registrazione allocazioni contabili
description: In questo argomento viene illustrato come elaborare una richiesta di allocazione in Dynamics 365 Finance.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e89aa21f988d50bc1a922e053be0ff2dcd196268
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834420"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="9ef21-103">Elaborare giornale di registrazione allocazioni contabili</span><span class="sxs-lookup"><span data-stu-id="9ef21-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ef21-104">In questo argomento viene illustrato come elaborare una richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="9ef21-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="9ef21-105">Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="9ef21-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="9ef21-106">Prima di creare un giornale di registrazione allocazioni, è necessario che esista almeno una regola di allocazione contabile attiva.</span><span class="sxs-lookup"><span data-stu-id="9ef21-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="9ef21-107">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="9ef21-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9ef21-108">Nel pannello di navigazione, andare a **Moduli > Contabilità generale > Allocazioni > Elabora richiesta di allocazione**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="9ef21-109">Nel campo **Regola** selezionare il record desiderato nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="9ef21-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="9ef21-110">Immettere una data nel campo **In data**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="9ef21-111">Il valore di **In data** è molto importante quando la contabilità generale è l'origine dati per la regola.</span><span class="sxs-lookup"><span data-stu-id="9ef21-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="9ef21-112">Questa data determina quali saldi contabili includere per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="9ef21-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="9ef21-113">Nel campo **Origine zero** selezionare **Interrompi**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="9ef21-114">Questa operazione interromperà il processo di allocazione e visualizzerà un messaggio indicante che è selezionato un importo di origine pari a zero.</span><span class="sxs-lookup"><span data-stu-id="9ef21-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="9ef21-115">Nel campo **Opzioni proposta**, selezionare **Solo proposta**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="9ef21-116">Selezionare **Solo proposta** per esaminare e facoltativamente approvare il risultato nei giornali di registrazione allocazioni prima della registrazione dell'allocazione nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="9ef21-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="9ef21-117">Immettere una data nel campo Data registrazione CoGe.</span><span class="sxs-lookup"><span data-stu-id="9ef21-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="9ef21-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-118">Select **OK**.</span></span>
7. <span data-ttu-id="9ef21-119">Nel pannello di navigazione, andare a **Moduli > Contabilità generale > Allocazioni > Giornali di registrazione allocazioni**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="9ef21-120">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-120">Select **Lines**.</span></span>
9. <span data-ttu-id="9ef21-121">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-121">Select **Post**.</span></span>
10. <span data-ttu-id="9ef21-122">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="9ef21-122">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]