--- 
title: Generare documenti elettronici per i pagamenti utilizzando configurazioni di formato
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può utilizzare una nuova configurazione del formato per la creazione di report elettronici (ER) per generare documenti elettronici per l'elaborazione dei pagamenti."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 805e6f377d452e9c50240c8c9fc2ea6f5cb487e6
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="generate-electronic-documents-for-payments-by-using-format-configurations"></a><span data-ttu-id="d92ba-103">Generare documenti elettronici per i pagamenti utilizzando configurazioni di formato</span><span class="sxs-lookup"><span data-stu-id="d92ba-103">Generate electronic documents for payments by using format configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d92ba-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può utilizzare una nuova configurazione del formato per la creazione di report elettronici (ER) per generare documenti elettronici per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="d92ba-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="d92ba-105">Questi passaggi possono essere eseguiti nella società campione.</span><span class="sxs-lookup"><span data-stu-id="d92ba-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="d92ba-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un documento per una configurazione con formato di pagamento".</span><span class="sxs-lookup"><span data-stu-id="d92ba-106">To complete these steps, you must first complete the steps in the “Create a configuration with format of payment document” procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="d92ba-107">Modificare la configurazione del metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="d92ba-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="d92ba-108">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="d92ba-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="d92ba-109">Attivare/disattivare la sezione Formato file per espanderla, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d92ba-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="d92ba-110">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="d92ba-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d92ba-111">Ad esempio, applicare un filtro al campo Metodo di pagamento in base a un valore "Elettronico".</span><span class="sxs-lookup"><span data-stu-id="d92ba-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="d92ba-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d92ba-112">Click Edit.</span></span>
5. <span data-ttu-id="d92ba-113">Impostare il campo Report elettronici generici su Sì.</span><span class="sxs-lookup"><span data-stu-id="d92ba-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="d92ba-114">Selezionare Sì per utilizzare il modello Report elettronici generici per la creazione dei file di pagamento.</span><span class="sxs-lookup"><span data-stu-id="d92ba-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="d92ba-115">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d92ba-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d92ba-116">Selezionare la configurazione del formato BACS (fittizia per il Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="d92ba-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="d92ba-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d92ba-117">Click Save.</span></span>
9. <span data-ttu-id="d92ba-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d92ba-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="d92ba-119">Testare il formato dei file di pagamento generati</span><span class="sxs-lookup"><span data-stu-id="d92ba-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="d92ba-120">Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="d92ba-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="d92ba-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d92ba-121">Click New.</span></span>
3. <span data-ttu-id="d92ba-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d92ba-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d92ba-123">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d92ba-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="d92ba-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d92ba-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d92ba-125">Selezionare VendPay.</span><span class="sxs-lookup"><span data-stu-id="d92ba-125">Select VendPay.</span></span>  
6. <span data-ttu-id="d92ba-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d92ba-126">Click Save.</span></span>
7. <span data-ttu-id="d92ba-127">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="d92ba-127">Click Lines.</span></span>
8. <span data-ttu-id="d92ba-128">Digitare "DEMF" nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="d92ba-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="d92ba-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="d92ba-129">DEMF</span></span>  
9. <span data-ttu-id="d92ba-130">Nel campo Account, specificare i valori desiderati "DE-01001".</span><span class="sxs-lookup"><span data-stu-id="d92ba-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="d92ba-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="d92ba-131">DE-01001</span></span>  
10. <span data-ttu-id="d92ba-132">Digitare "Pagamento" nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="d92ba-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="d92ba-133">Pagamento</span><span class="sxs-lookup"><span data-stu-id="d92ba-133">Payment</span></span>  
11. <span data-ttu-id="d92ba-134">Nel campo Dare immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d92ba-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="d92ba-135">1000</span><span class="sxs-lookup"><span data-stu-id="d92ba-135">1000</span></span>  
12. <span data-ttu-id="d92ba-136">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="d92ba-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="d92ba-137">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d92ba-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d92ba-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d92ba-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d92ba-139">Selezionare il valore elettronico.</span><span class="sxs-lookup"><span data-stu-id="d92ba-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="d92ba-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d92ba-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="d92ba-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d92ba-141">Click Save.</span></span>
17. <span data-ttu-id="d92ba-142">Fare clic su Genera pagamenti.</span><span class="sxs-lookup"><span data-stu-id="d92ba-142">Click Generate payments.</span></span>
18. <span data-ttu-id="d92ba-143">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d92ba-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d92ba-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d92ba-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d92ba-145">Selezionare il valore elettronico.</span><span class="sxs-lookup"><span data-stu-id="d92ba-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="d92ba-146">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d92ba-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d92ba-147">Selezionare il valore elettronico.</span><span class="sxs-lookup"><span data-stu-id="d92ba-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="d92ba-148">Digitare un valore nel campo Nome file.</span><span class="sxs-lookup"><span data-stu-id="d92ba-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="d92ba-149">Ad esempio, digitare "pagamenti".</span><span class="sxs-lookup"><span data-stu-id="d92ba-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="d92ba-150">Nel campo Conto bancario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d92ba-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="d92ba-151">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d92ba-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d92ba-152">Selezionare il valore GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="d92ba-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="d92ba-153">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d92ba-153">Click OK.</span></span>
25. <span data-ttu-id="d92ba-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d92ba-154">Click OK.</span></span>
    * <span data-ttu-id="d92ba-155">Analizzare il file di pagamento creato in formato XML.</span><span class="sxs-lookup"><span data-stu-id="d92ba-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="d92ba-156">Confrontarlo con il layout del documento progettato e gli attributi di transazione del pagamento definiti.</span><span class="sxs-lookup"><span data-stu-id="d92ba-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  


