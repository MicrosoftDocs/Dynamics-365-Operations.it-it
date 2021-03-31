---
title: Liquidare un assegno postdatato di un cliente
description: Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abcd6532c294223e768d1a01d97309e35c30edbe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217412"
---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="22989-103">Liquidare un assegno postdatato di un cliente</span><span class="sxs-lookup"><span data-stu-id="22989-103">Settle a postdated check from a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="22989-104">Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca.</span><span class="sxs-lookup"><span data-stu-id="22989-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="22989-105">Questa transazione finanziaria liquida inoltre la transazione del conto provvisorio per l'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="22989-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="22989-106">Completare le seguenti attività prima di iniziare la presente.</span><span class="sxs-lookup"><span data-stu-id="22989-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="22989-107">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="22989-107">Set up postdated checks</span></span>

2) <span data-ttu-id="22989-108">Registrare un assegno postdatato per un cliente</span><span class="sxs-lookup"><span data-stu-id="22989-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="22989-109">Il ruolo dell'attività è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="22989-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="22989-110">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="22989-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="22989-111">Andare a Crediti e riscossioni > Richieste di informazioni e report > Pagamenti > Assegni postdatati cliente.</span><span class="sxs-lookup"><span data-stu-id="22989-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="22989-112">Fare clic su Liquida.</span><span class="sxs-lookup"><span data-stu-id="22989-112">Click Settle.</span></span>
3. <span data-ttu-id="22989-113">Fare clic su Liquida voci di compensazione.</span><span class="sxs-lookup"><span data-stu-id="22989-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="22989-114">Liquidare il conto cliente per la transazione assegno.</span><span class="sxs-lookup"><span data-stu-id="22989-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="22989-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="22989-115">Close the page.</span></span>
5. <span data-ttu-id="22989-116">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="22989-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="22989-117">Selezionare un'opzione nel campo Mostra.</span><span class="sxs-lookup"><span data-stu-id="22989-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="22989-118">Selezionare o deselezionare la casella di controllo Mostra solo giornali creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="22989-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="22989-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="22989-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="22989-120">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="22989-120">Click Lines.</span></span>
10. <span data-ttu-id="22989-121">Fare clic su Giustificativo.</span><span class="sxs-lookup"><span data-stu-id="22989-121">Click Voucher.</span></span>
11. <span data-ttu-id="22989-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="22989-122">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]