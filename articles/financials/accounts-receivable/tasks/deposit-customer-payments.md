---
title: Depositare pagamenti clienti
description: Depositare pagamenti cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595d1b609ae83af8f1581caeff9ef7d3892a6207
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867776"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="6bc14-103">Depositare pagamenti clienti</span><span class="sxs-lookup"><span data-stu-id="6bc14-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6bc14-104">Depositare pagamenti cliente.</span><span class="sxs-lookup"><span data-stu-id="6bc14-104">Deposit customer payments.</span></span> <span data-ttu-id="6bc14-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="6bc14-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="6bc14-106">Andare a **Pannello di navigazione > Moduli > Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="6bc14-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-107">Select **New**.</span></span>
3. <span data-ttu-id="6bc14-108">Nel campo **Nome**, selezionare **CustPay** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="6bc14-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="6bc14-109">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-109">Select **Lines**.</span></span>
5. <span data-ttu-id="6bc14-110">Nel campo **Conto** selezionare il cliente per il quale si sta registrando il pagamento.</span><span class="sxs-lookup"><span data-stu-id="6bc14-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="6bc14-111">Nel campo **Avere**, immettere l'importo del pagamento.</span><span class="sxs-lookup"><span data-stu-id="6bc14-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="6bc14-112">È possibile scegliere di lasciare l'importo vuoto e farlo calcolare dal sistema selezionando le fatture che sono state pagate.</span><span class="sxs-lookup"><span data-stu-id="6bc14-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="6bc14-113">Digitare un valore nel campo **Riferimento di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="6bc14-114">Il riferimento di pagamento può essere il numero di assegno per il pagamento che si immette.</span><span class="sxs-lookup"><span data-stu-id="6bc14-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="6bc14-115">Il riferimento di pagamento è necessario per includere il pagamento in una distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="6bc14-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="6bc14-116">Contrassegnare la casella Utilizzo di una distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="6bc14-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="6bc14-117">Se il pagamento deve essere incluso nel deposito, modificare questa impostazione su Sì.</span><span class="sxs-lookup"><span data-stu-id="6bc14-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="6bc14-118">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-118">Select **New**.</span></span>
10. <span data-ttu-id="6bc14-119">Nel campo **Conto** selezionare il cliente per il pagamento successivo.</span><span class="sxs-lookup"><span data-stu-id="6bc14-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="6bc14-120">Nel campo **Avere**, immettere l'importo del pagamento.</span><span class="sxs-lookup"><span data-stu-id="6bc14-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="6bc14-121">Digitare un valore nel campo **Riferimento di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="6bc14-122">Contrassegnare la casella **Utilizzo di una distinta di deposito**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="6bc14-123">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-123">Select **Post**.</span></span> <span data-ttu-id="6bc14-124">I pagamenti devono essere registrati prima che la distinta di deposito possa essere generata.</span><span class="sxs-lookup"><span data-stu-id="6bc14-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="6bc14-125">In questo modo è possibile garantire che i pagamenti non cambino dopo che la distinta di deposito viene generata.</span><span class="sxs-lookup"><span data-stu-id="6bc14-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="6bc14-126">Selezionare **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-126">Select **Functions**.</span></span>
16. <span data-ttu-id="6bc14-127">Selezionare **Distinta di deposito**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="6bc14-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-128">Select **OK**.</span></span> <span data-ttu-id="6bc14-129">La prima pagina viene utilizzata per creare la distinta di deposito.</span><span class="sxs-lookup"><span data-stu-id="6bc14-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="6bc14-130">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6bc14-130">Select **OK**.</span></span> <span data-ttu-id="6bc14-131">Il secondo passaggio è di stampare la distinta di deposito, ma questo passaggio non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6bc14-131">The second step is to print the deposit slip, but this step is not required.</span></span>  

