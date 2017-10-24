--- 
title: Elaborare giornale di registrazione allocazioni contabili
description: "Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7d299657758b1e1322aef07bfe8c71f7bf00b0ca
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="637bf-103">Elaborare giornale di registrazione allocazioni contabili</span><span class="sxs-lookup"><span data-stu-id="637bf-103">Process ledger allocation journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="637bf-104">Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="637bf-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="637bf-105">Prima di creare un giornale di registrazione allocazioni, è necessario che esista almeno una regola di allocazione contabile attiva.</span><span class="sxs-lookup"><span data-stu-id="637bf-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="637bf-106">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="637bf-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="637bf-107">Andare a Contabilità generale > Allocazioni > Elabora richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="637bf-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="637bf-108">Nel campo Regola fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="637bf-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="637bf-109">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="637bf-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="637bf-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="637bf-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="637bf-111">Immettere una data nel campo In data.</span><span class="sxs-lookup"><span data-stu-id="637bf-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="637bf-112">Il valore di In data è molto importante quando la contabilità generale è l'origine dati per la regola.</span><span class="sxs-lookup"><span data-stu-id="637bf-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="637bf-113">Questa data determina quali saldi contabili includere per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="637bf-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="637bf-114">Nel campo Origine zero selezionare Interrompi.</span><span class="sxs-lookup"><span data-stu-id="637bf-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="637bf-115">Questo interromperà il processo di allocazione e visualizzerà un messaggio indicante che è selezionato un importo di origine pari a zero.</span><span class="sxs-lookup"><span data-stu-id="637bf-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="637bf-116">Nel campo Opzioni proposta, selezionare 'Solo proposta'.</span><span class="sxs-lookup"><span data-stu-id="637bf-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="637bf-117">Selezionare Solo proposta per esaminare e facoltativamente approvare il risultato nei giornali di registrazione allocazioni prima della registrazione dell'allocazione nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="637bf-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="637bf-118">Immettere una data nel campo Data registrazione CoGe.</span><span class="sxs-lookup"><span data-stu-id="637bf-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="637bf-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="637bf-119">Click OK.</span></span>
9. <span data-ttu-id="637bf-120">Andare a Contabilità generale > Allocazioni > Giornali di registrazione allocazioni.</span><span class="sxs-lookup"><span data-stu-id="637bf-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="637bf-121">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="637bf-121">Click Lines.</span></span>
11. <span data-ttu-id="637bf-122">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="637bf-122">Click Post.</span></span>
12. <span data-ttu-id="637bf-123">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="637bf-123">Click Post.</span></span>


