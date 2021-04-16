---
title: Liquidare un assegno postdatato per un fornitore
description: Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89acad0c9421960ff4d07ed8eec798b9068424d5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834573"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="46cdd-103">Liquidare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="46cdd-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46cdd-104">Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca.</span><span class="sxs-lookup"><span data-stu-id="46cdd-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="46cdd-105">Completare le seguenti procedure prima di iniziare la presente.</span><span class="sxs-lookup"><span data-stu-id="46cdd-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="46cdd-106">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="46cdd-106">Set up postdated checks</span></span>

2) <span data-ttu-id="46cdd-107">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="46cdd-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="46cdd-108">Il ruolo di questa procedura è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="46cdd-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="46cdd-109">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="46cdd-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="46cdd-110">Andare a Contabilità fornitori > Pagamenti > Assegni postdatati fornitore.</span><span class="sxs-lookup"><span data-stu-id="46cdd-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="46cdd-111">Fare clic su Liquida.</span><span class="sxs-lookup"><span data-stu-id="46cdd-111">Click Settle.</span></span>
3. <span data-ttu-id="46cdd-112">Fare clic su Liquida voci di compensazione.</span><span class="sxs-lookup"><span data-stu-id="46cdd-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="46cdd-113">Liquidare il conto fornitore per la transazione assegno.</span><span class="sxs-lookup"><span data-stu-id="46cdd-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="46cdd-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="46cdd-114">Close the page.</span></span>
5. <span data-ttu-id="46cdd-115">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="46cdd-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="46cdd-116">Nel campo Mostra, selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="46cdd-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="46cdd-117">Selezionare o deselezionare la casella di controllo Mostra solo giornali creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="46cdd-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="46cdd-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="46cdd-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="46cdd-119">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="46cdd-119">Click Lines.</span></span>
10. <span data-ttu-id="46cdd-120">Fare clic su Giustificativo.</span><span class="sxs-lookup"><span data-stu-id="46cdd-120">Click Voucher.</span></span>
11. <span data-ttu-id="46cdd-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="46cdd-121">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]