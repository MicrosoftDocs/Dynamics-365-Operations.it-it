--- 
title: "Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione"
description: "Questa guida attività indicherà come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 604345d357e5019e334017b2b6d0413f40818acc
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="a7603-103">Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione</span><span class="sxs-lookup"><span data-stu-id="a7603-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a7603-104">Questa guida attività indicherà come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.</span><span class="sxs-lookup"><span data-stu-id="a7603-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="a7603-105">Creare e registrare una fattura</span><span class="sxs-lookup"><span data-stu-id="a7603-105">Create and post and invoice</span></span>
1. <span data-ttu-id="a7603-106">Andare a Contabilità fornitori > Fatture > Registro fatture.</span><span class="sxs-lookup"><span data-stu-id="a7603-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="a7603-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a7603-107">Click New.</span></span>
3. <span data-ttu-id="a7603-108">Selezionare il nome del registro fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a7603-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="a7603-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a7603-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a7603-110">Fare clic su Righe per aprire il registro e immettere le righe di spesa.</span><span class="sxs-lookup"><span data-stu-id="a7603-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="a7603-111">Selezionare un fornitore.</span><span class="sxs-lookup"><span data-stu-id="a7603-111">Select a vendor.</span></span> <span data-ttu-id="a7603-112">Ad esempio, immettere o selezionare US-104</span><span class="sxs-lookup"><span data-stu-id="a7603-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="a7603-113">Digitare un valore nel campo Fattura.</span><span class="sxs-lookup"><span data-stu-id="a7603-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="a7603-114">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="a7603-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="a7603-115">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="a7603-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="a7603-116">Nel campo Approvata da fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7603-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a7603-117">Evidenzi un approvatore e fare clic su per selezionare tale approvatore.</span><span class="sxs-lookup"><span data-stu-id="a7603-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="a7603-118">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="a7603-118">Click Post.</span></span>
13. <span data-ttu-id="a7603-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7603-119">Close the page.</span></span>
14. <span data-ttu-id="a7603-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7603-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="a7603-121">Approvare una fattura</span><span class="sxs-lookup"><span data-stu-id="a7603-121">Approve an invoice</span></span>
1. <span data-ttu-id="a7603-122">Andare a Contabilità fornitori > Fatture > Approvazione fattura.</span><span class="sxs-lookup"><span data-stu-id="a7603-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="a7603-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a7603-123">Click New.</span></span>
3. <span data-ttu-id="a7603-124">Selezionare il nome del giornale di approvazione fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a7603-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="a7603-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a7603-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a7603-126">Fare clic sulle righe per visualizzare una pagina in cui sarà possibile selezionare le fatture che si desidera approvare.</span><span class="sxs-lookup"><span data-stu-id="a7603-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="a7603-127">Selezionare Trova giustificativi per visualizzare tutte le fatture pronte per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="a7603-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="a7603-128">Contrassegnare la fattura creata.</span><span class="sxs-lookup"><span data-stu-id="a7603-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="a7603-129">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="a7603-129">Click Select.</span></span>
    * <span data-ttu-id="a7603-130">I giustificativi selezionati in precedenza vengono spostati in questo elenco dopo che sono stati selezionati.</span><span class="sxs-lookup"><span data-stu-id="a7603-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="a7603-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a7603-131">Click OK.</span></span>
10. <span data-ttu-id="a7603-132">Fare clic su nel campo relativo al numero di conto per aggiungere un conto spese nella fattura.</span><span class="sxs-lookup"><span data-stu-id="a7603-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="a7603-133">Immettere un numero di conto e uscire dal campo.</span><span class="sxs-lookup"><span data-stu-id="a7603-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="a7603-134">Ad esempio, immettere 600120.</span><span class="sxs-lookup"><span data-stu-id="a7603-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="a7603-135">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="a7603-135">Click Post.</span></span>
13. <span data-ttu-id="a7603-136">Fare clic su Giustificativo per visualizzare le voci registrate.</span><span class="sxs-lookup"><span data-stu-id="a7603-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="a7603-137">Il conto di approvazione fatture in sospeso viene stornato e sostituito con il conto spese effettivo.</span><span class="sxs-lookup"><span data-stu-id="a7603-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

