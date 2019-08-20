---
title: Elaborare giornale di registrazione allocazioni contabili
description: Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 087bd4f203e8762447e823b19076b79296a390d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846369"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="b1291-103">Elaborare giornale di registrazione allocazioni contabili</span><span class="sxs-lookup"><span data-stu-id="b1291-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b1291-104">Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="b1291-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="b1291-105">Prima di creare un giornale di registrazione allocazioni, è necessario che esista almeno una regola di allocazione contabile attiva.</span><span class="sxs-lookup"><span data-stu-id="b1291-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="b1291-106">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="b1291-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b1291-107">Andare a Contabilità generale > Allocazioni > Elabora richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="b1291-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="b1291-108">Nel campo Regola fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b1291-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b1291-109">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b1291-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b1291-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b1291-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b1291-111">Immettere una data nel campo In data.</span><span class="sxs-lookup"><span data-stu-id="b1291-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="b1291-112">Il valore di In data è molto importante quando la contabilità generale è l'origine dati per la regola.</span><span class="sxs-lookup"><span data-stu-id="b1291-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="b1291-113">Questa data determina quali saldi contabili includere per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="b1291-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="b1291-114">Nel campo Origine zero selezionare Interrompi.</span><span class="sxs-lookup"><span data-stu-id="b1291-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="b1291-115">Questo interromperà il processo di allocazione e visualizzerà un messaggio indicante che è selezionato un importo di origine pari a zero.</span><span class="sxs-lookup"><span data-stu-id="b1291-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="b1291-116">Nel campo Opzioni proposta, selezionare 'Solo proposta'.</span><span class="sxs-lookup"><span data-stu-id="b1291-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="b1291-117">Selezionare Solo proposta per esaminare e facoltativamente approvare il risultato nei giornali di registrazione allocazioni prima della registrazione dell'allocazione nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="b1291-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="b1291-118">Immettere una data nel campo Data registrazione CoGe.</span><span class="sxs-lookup"><span data-stu-id="b1291-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="b1291-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b1291-119">Click OK.</span></span>
9. <span data-ttu-id="b1291-120">Andare a Contabilità generale > Allocazioni > Giornali di registrazione allocazioni.</span><span class="sxs-lookup"><span data-stu-id="b1291-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="b1291-121">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="b1291-121">Click Lines.</span></span>
11. <span data-ttu-id="b1291-122">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="b1291-122">Click Post.</span></span>
12. <span data-ttu-id="b1291-123">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="b1291-123">Click Post.</span></span>

