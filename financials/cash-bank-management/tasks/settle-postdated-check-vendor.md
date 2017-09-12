--- 
title: Liquidare un assegno postdatato per un fornitore
description: "Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ac3fcad40e2d71dbde5fab8d1aa77cbfa879cdb1
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="90a31-103">Liquidare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="90a31-103">Settle a postdated check for a vendor</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="90a31-104">Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca.</span><span class="sxs-lookup"><span data-stu-id="90a31-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="90a31-105">Completare le seguenti procedure prima di iniziare la presente.</span><span class="sxs-lookup"><span data-stu-id="90a31-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="90a31-106">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="90a31-106">Set up postdated checks</span></span>

2) <span data-ttu-id="90a31-107">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="90a31-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="90a31-108">Il ruolo di questa procedura è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="90a31-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="90a31-109">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="90a31-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="90a31-110">Andare a Contabilità fornitori > Pagamenti > Assegni postdatati fornitore.</span><span class="sxs-lookup"><span data-stu-id="90a31-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="90a31-111">Fare clic su Liquida.</span><span class="sxs-lookup"><span data-stu-id="90a31-111">Click Settle.</span></span>
3. <span data-ttu-id="90a31-112">Fare clic su Liquida voci di compensazione.</span><span class="sxs-lookup"><span data-stu-id="90a31-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="90a31-113">Liquidare il conto fornitore per la transazione assegno.</span><span class="sxs-lookup"><span data-stu-id="90a31-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="90a31-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="90a31-114">Close the page.</span></span>
5. <span data-ttu-id="90a31-115">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="90a31-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="90a31-116">Nel campo Mostra, selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="90a31-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="90a31-117">Selezionare o deselezionare la casella di controllo Mostra solo giornali creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="90a31-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="90a31-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="90a31-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="90a31-119">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="90a31-119">Click Lines.</span></span>
10. <span data-ttu-id="90a31-120">Fare clic su Giustificativo.</span><span class="sxs-lookup"><span data-stu-id="90a31-120">Click Voucher.</span></span>
11. <span data-ttu-id="90a31-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="90a31-121">Close the page.</span></span>


