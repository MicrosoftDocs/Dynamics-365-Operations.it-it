--- 
title: Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia
description: "Questa attività crea una linea di credito bancaria e un profilo di registrazione necessari per l'elaborazione di una lettera di garanzia."
author: kweekley
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: b78f82b60ee72bb91a4dd4aa13776eb8b74d7367
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="f091d-103">Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia</span><span class="sxs-lookup"><span data-stu-id="f091d-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f091d-104">Questa attività crea una linea di credito bancaria e un profilo di registrazione necessari per l'elaborazione di una lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="f091d-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="f091d-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="f091d-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="f091d-106">Parametro di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="f091d-106">General ledger parameter</span></span>
1. <span data-ttu-id="f091d-107">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="f091d-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="f091d-108">Espandere la sezione Documento bancario.</span><span class="sxs-lookup"><span data-stu-id="f091d-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="f091d-109">Selezionare l'opzione Abilita lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="f091d-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="f091d-110">Nel campo Giornale di registrazione transazioni fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f091d-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f091d-111">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f091d-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="f091d-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f091d-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="f091d-113">Fare clic sulla scheda Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="f091d-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="f091d-114">Definire il codice di sequenza numerica per il numero della lettera di garanzia e i riferimenti di transazione della lettera di garanzia</span><span class="sxs-lookup"><span data-stu-id="f091d-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="f091d-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f091d-115">Click Save.</span></span>
9. <span data-ttu-id="f091d-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f091d-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="f091d-117">Creare una linea di credito bancaria</span><span class="sxs-lookup"><span data-stu-id="f091d-117">Create Bank facility</span></span>
1. <span data-ttu-id="f091d-118">Andare a Gestione cassa e banche > Impostazioni > Linee di credito bancarie.</span><span class="sxs-lookup"><span data-stu-id="f091d-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="f091d-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f091d-119">Click New.</span></span>
3. <span data-ttu-id="f091d-120">Nel campo Gruppo di linee di credito immettere il nome del gruppo di linee di credito bancarie per la transazione della lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="f091d-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="f091d-121">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="f091d-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f091d-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f091d-122">Click Save.</span></span>
6. <span data-ttu-id="f091d-123">Fare clic sulla scheda Tipi di linee di credito.</span><span class="sxs-lookup"><span data-stu-id="f091d-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="f091d-124">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f091d-124">Click New.</span></span>
8. <span data-ttu-id="f091d-125">Nel campo Tipo di linea di credito immettere il nome del tipo di linea di credito bancaria correlato al contratto per linea di credito bancaria.</span><span class="sxs-lookup"><span data-stu-id="f091d-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="f091d-126">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="f091d-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="f091d-127">Nel campo Gruppo di linee di credito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f091d-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f091d-128">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f091d-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="f091d-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f091d-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="f091d-130">Selezionare un'opzione nel campo Natura linea di credito.</span><span class="sxs-lookup"><span data-stu-id="f091d-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="f091d-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f091d-131">Click Save.</span></span>
15. <span data-ttu-id="f091d-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f091d-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="f091d-133">Profilo di registrazione bancaria</span><span class="sxs-lookup"><span data-stu-id="f091d-133">Bank posting profile</span></span>
1. <span data-ttu-id="f091d-134">Andare a Gestione cassa e banche > Impostazioni > Profilo di registrazione documenti bancari.</span><span class="sxs-lookup"><span data-stu-id="f091d-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="f091d-135">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f091d-135">Click New.</span></span>
3. <span data-ttu-id="f091d-136">Nel campo Numero conto/gruppo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f091d-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f091d-137">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f091d-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f091d-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f091d-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f091d-139">Nel campo Conto di liquidazione selezionare il conto principale per la liquidazione.</span><span class="sxs-lookup"><span data-stu-id="f091d-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="f091d-140">Nel campo Conto spese selezionare il conto per le transazioni di spesa.</span><span class="sxs-lookup"><span data-stu-id="f091d-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="f091d-141">Nel campo Conto a margine selezionare il conto per la transazione a margine.</span><span class="sxs-lookup"><span data-stu-id="f091d-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="f091d-142">Nel campo Conto di liquidazione selezionare il conto di liquidazione per la transazione della lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="f091d-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="f091d-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f091d-143">Click Save.</span></span>
11. <span data-ttu-id="f091d-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f091d-144">Close the page.</span></span>


