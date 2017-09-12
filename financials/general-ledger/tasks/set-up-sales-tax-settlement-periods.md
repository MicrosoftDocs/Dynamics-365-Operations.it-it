--- 
title: Imposta i periodi di liquidazione IVA
description: I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata.
author: twheeloc
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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4d65dee3bd059966458cb9603807de85b704fc49
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="e3aa3-103">Imposta i periodi di liquidazione IVA</span><span class="sxs-lookup"><span data-stu-id="e3aa3-103">Set up sales tax settlement periods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3aa3-104">I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="e3aa3-105">Un processo di liquidazione può essere eseguito per un periodo di liquidazione per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="e3aa3-106">Tutti i codici IVA associati al periodo di liquidazione verranno liquidati.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="e3aa3-107">A seconda dell'impostazione dell'ufficio IVA correlato, la soggettività tributaria viene registrata in un conto fornitore o CoGe.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="e3aa3-108">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="e3aa3-109">Andare a Imposta > Imposte indirette > IVA > Periodi liquidazione IVA.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="e3aa3-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-110">Click New.</span></span>
3. <span data-ttu-id="e3aa3-111">Nel campo Periodo di liquidazione digitare un calore.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="e3aa3-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e3aa3-113">Nel campo Ufficio selezionare l'ufficio IVA che riceve i report e i pagamenti creati per il periodo di liquidazione.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="e3aa3-114">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="e3aa3-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e3aa3-116">Nel campo Termini di pagamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e3aa3-117">L'ufficio IVA relativo può essere impostato come fornitore e la liquidazione VAT creerà una fattura fornitore aperta.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="e3aa3-118">Termini di pagamento definisce la data di scadenza della fattura fornitore aperta.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="e3aa3-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="e3aa3-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="e3aa3-121">Selezionare un tipo per gli intervalli del periodo di liquidazione.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="e3aa3-122">Immettere il numero di unità dell'intervallo periodico per periodo.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="e3aa3-123">Ad esempio, un trimestre ha 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="e3aa3-124">Selezionare o deselezionare la casella di controllo Utilizza elaborazione batch per liquidazione IVA.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="e3aa3-125">Il processo di liquidazione per il periodo di liquidazione può essere elaborato come processo batch in background.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="e3aa3-126">Si consigliano tantissime transazioni IVA all'interno di un intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="e3aa3-127">Espandere la scheda Intervalli periodici.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-127">Expand the Period intervals tab.</span></span>
15. <span data-ttu-id="e3aa3-128">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-128">Click Add.</span></span>
16. <span data-ttu-id="e3aa3-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-129">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="e3aa3-130">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-130">In the From date field, enter a date.</span></span>
18. <span data-ttu-id="e3aa3-131">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-131">In the To date field, enter a date.</span></span>
19. <span data-ttu-id="e3aa3-132">Fare clic su Nuovo intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-132">Click New period interval.</span></span>
    * <span data-ttu-id="e3aa3-133">Una volta che il primo intervallo periodico è stato immesso, i nuovi periodi possono essere creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="e3aa3-134">È possibile tornare e aggiungere nuovi intervalli periodici in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-134">You can come back and add new period intervals as required.</span></span>  
20. <span data-ttu-id="e3aa3-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-135">Close the page.</span></span>

