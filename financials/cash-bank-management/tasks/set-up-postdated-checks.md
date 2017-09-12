--- 
title: Impostare gli assegni postdatati
description: In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.
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
ms.openlocfilehash: 1d05580684b9e8bef3cfa84e8af5b8a71f655084
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="93cc1-103">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="93cc1-103">Set up postdated checks</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93cc1-104">In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="93cc1-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="93cc1-105">È inoltre possibile specificare i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="93cc1-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="93cc1-106">Gli assegni postdatati che sono emessi per effettuare e ricevere pagamenti in una data futura.</span><span class="sxs-lookup"><span data-stu-id="93cc1-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="93cc1-107">È possibile specificare se l'assegno deve essere riportato nei libri contabili prima della relativa data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="93cc1-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="93cc1-108">Il ruolo di questa procedura è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="93cc1-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="93cc1-109">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="93cc1-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="93cc1-110">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="93cc1-110">Set up postdated checks</span></span>
1. <span data-ttu-id="93cc1-111">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="93cc1-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="93cc1-112">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="93cc1-113">Selezionare o deselezionare la casella di controllo Abilita assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="93cc1-114">Selezionare o deselezionare la casella di controllo Inserimenti nel giornale di registrazione per assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="93cc1-115">Nel campo Conto di compensazione per assegni emessi specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="93cc1-116">Nel campo Conto di compensazione per assegni ricevuti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="93cc1-117">Nel campo Giornale di registrazione generale per voci di compensazione immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="93cc1-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="93cc1-118">Nel campo Trasferisci assegni postdatati a questo giornale di registrazione pagamenti fornitore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="93cc1-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="93cc1-119">Nel campo Conto di compensazione per ritenuta d'acconto specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="93cc1-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="93cc1-120">Click Save.</span></span>
11. <span data-ttu-id="93cc1-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93cc1-121">Close the page.</span></span>
12. <span data-ttu-id="93cc1-122">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="93cc1-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="93cc1-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="93cc1-123">Click New.</span></span>
14. <span data-ttu-id="93cc1-124">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="93cc1-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="93cc1-125">Selezionare l'opzione Registrazione compensazione assegni postdatati per indicare che l'importo dell'assegno viene registrato in un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="93cc1-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="93cc1-126">Nel campo Tipo di conto selezionare "Banca".</span><span class="sxs-lookup"><span data-stu-id="93cc1-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="93cc1-127">Il conto di contropartita del metodo di pagamento sarà una banca.</span><span class="sxs-lookup"><span data-stu-id="93cc1-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="93cc1-128">Nel campo Conto pagamenti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="93cc1-129">Selezionare il conto bancario utilizzato per detrarre l'importo della fattura.</span><span class="sxs-lookup"><span data-stu-id="93cc1-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="93cc1-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93cc1-130">Close the page.</span></span>
19. <span data-ttu-id="93cc1-131">Scegliere Contabilità clienti > Impostazione pagamenti > Metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="93cc1-131">Go to Accounts receivable > Payment setup > Methods of payment</span></span>
20. <span data-ttu-id="93cc1-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="93cc1-132">Click New.</span></span>
21. <span data-ttu-id="93cc1-133">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="93cc1-133">In the Method of payment field, type a value.</span></span>
22. <span data-ttu-id="93cc1-134">Selezionare l'opzione Registrazione compensazione assegni postdatati per indicare che l'importo dell'assegno viene registrato in un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="93cc1-134">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
23. <span data-ttu-id="93cc1-135">Nel campo Tipo di conto selezionare "Banca".</span><span class="sxs-lookup"><span data-stu-id="93cc1-135">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="93cc1-136">Il conto di contropartita del metodo di pagamento sarà una banca.</span><span class="sxs-lookup"><span data-stu-id="93cc1-136">The offset account of the payment method will be a bank.</span></span>  
24. <span data-ttu-id="93cc1-137">Nel campo Conto pagamenti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="93cc1-137">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="93cc1-138">Selezionare il conto bancario utilizzato per detrarre l'importo della fattura.</span><span class="sxs-lookup"><span data-stu-id="93cc1-138">Select the bank account that is used to deduct the invoice amount.</span></span>  
25. <span data-ttu-id="93cc1-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93cc1-139">Close the page.</span></span>

