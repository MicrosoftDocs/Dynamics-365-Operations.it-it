--- 
title: Depositare pagamenti clienti
description: Depositare pagamenti cliente.
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dbf21bd5df70cd80e4fe3f2f5d699aa82b62423b
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="deposit-customer-payments"></a><span data-ttu-id="be57f-103">Depositare pagamenti clienti</span><span class="sxs-lookup"><span data-stu-id="be57f-103">Deposit customer payments</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="be57f-104">Depositare pagamenti cliente.</span><span class="sxs-lookup"><span data-stu-id="be57f-104">Deposit customer payments.</span></span> <span data-ttu-id="be57f-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="be57f-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="be57f-106">Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="be57f-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="be57f-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="be57f-107">Click New.</span></span>
3. <span data-ttu-id="be57f-108">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="be57f-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="be57f-109">Selezionare il giornale di registrazione pagamento.</span><span class="sxs-lookup"><span data-stu-id="be57f-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="be57f-110">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="be57f-110">Click Lines.</span></span>
6. <span data-ttu-id="be57f-111">Nel campo Conto selezionare il cliente per il quale si sta registrando il pagamento.</span><span class="sxs-lookup"><span data-stu-id="be57f-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="be57f-112">Nel campo Avere, immettere l'importo del pagamento.</span><span class="sxs-lookup"><span data-stu-id="be57f-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="be57f-113">È possibile scegliere di lasciare l'importo vuoto e farlo calcolare dal sistema selezionando le fatture che sono state pagate.</span><span class="sxs-lookup"><span data-stu-id="be57f-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="be57f-114">Digitare un valore nel campo Riferimento di pagamento.</span><span class="sxs-lookup"><span data-stu-id="be57f-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="be57f-115">Il riferimento di pagamento può essere il numero di assegno per il pagamento che si immette.</span><span class="sxs-lookup"><span data-stu-id="be57f-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="be57f-116">Il riferimento di pagamento è necessario per includere il pagamento in una distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="be57f-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="be57f-117">Contrassegnare la casella Utilizzo di una distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="be57f-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="be57f-118">Se il pagamento deve essere incluso nel deposito, modificare questa impostazione su Sì.</span><span class="sxs-lookup"><span data-stu-id="be57f-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="be57f-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="be57f-119">Click New.</span></span>
11. <span data-ttu-id="be57f-120">Nel campo Conto selezionare il cliente per il pagamento successivo.</span><span class="sxs-lookup"><span data-stu-id="be57f-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="be57f-121">Nel campo Avere, immettere l'importo del pagamento.</span><span class="sxs-lookup"><span data-stu-id="be57f-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="be57f-122">Digitare un valore nel campo Riferimento di pagamento.</span><span class="sxs-lookup"><span data-stu-id="be57f-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="be57f-123">Contrassegnare la casella Utilizzo di una distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="be57f-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="be57f-124">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="be57f-124">Click Post.</span></span>
    * <span data-ttu-id="be57f-125">I pagamenti devono essere registrati prima che la distinta di deposito possa essere generata.</span><span class="sxs-lookup"><span data-stu-id="be57f-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="be57f-126">In questo modo è possibile garantire che i pagamenti non cambino dopo che la distinta di deposito viene generata.</span><span class="sxs-lookup"><span data-stu-id="be57f-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="be57f-127">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="be57f-127">Click Functions.</span></span>
17. <span data-ttu-id="be57f-128">Fare clic su Distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="be57f-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="be57f-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="be57f-129">Click OK.</span></span>
    * <span data-ttu-id="be57f-130">La prima pagina viene utilizzata per creare la distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="be57f-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="be57f-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="be57f-131">Click OK.</span></span>
    * <span data-ttu-id="be57f-132">Il secondo passaggio è di stampare la distinta di deposito, ma questo passaggio non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="be57f-132">The second step is to print the deposit slip, but this step is not required.</span></span>  


