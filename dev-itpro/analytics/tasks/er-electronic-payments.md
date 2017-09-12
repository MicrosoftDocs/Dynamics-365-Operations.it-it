--- 
title: Generare documenti elettronici per i pagamenti utilizzando una configurazione di formato per la creazione di report elettronici (ER)
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8a04918d6642de73016231fdb96d9ea6b0be5999
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="5921f-103">Generare documenti elettronici per i pagamenti utilizzando una configurazione di formato per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="5921f-103">Generate electronic documents for payments using a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5921f-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può utilizzare una nuova configurazione del formato per la creazione di report elettronici (ER) per generare documenti elettronici per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="5921f-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="5921f-105">Questi passaggi possono essere eseguiti nella società campione.</span><span class="sxs-lookup"><span data-stu-id="5921f-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="5921f-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un documento per una configurazione con formato di pagamento".</span><span class="sxs-lookup"><span data-stu-id="5921f-106">To complete these steps, you must first complete the steps in the “Create a configuration with format of payment document” procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="5921f-107">Modificare la configurazione del metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="5921f-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="5921f-108">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5921f-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="5921f-109">Attivare/disattivare la sezione Formato file per espanderla, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5921f-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="5921f-110">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="5921f-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5921f-111">Ad esempio, applicare un filtro al campo Metodo di pagamento in base a un valore "Elettronico".</span><span class="sxs-lookup"><span data-stu-id="5921f-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="5921f-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="5921f-112">Click Edit.</span></span>
5. <span data-ttu-id="5921f-113">Impostare il campo Report elettronici generici su Sì.</span><span class="sxs-lookup"><span data-stu-id="5921f-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="5921f-114">Selezionare Sì per utilizzare il modello Report elettronici generici per la creazione dei file di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5921f-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="5921f-115">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5921f-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5921f-116">Selezionare la configurazione del formato BACS (fittizia per il Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="5921f-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="5921f-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5921f-117">Click Save.</span></span>
9. <span data-ttu-id="5921f-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5921f-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="5921f-119">Testare il formato dei file di pagamento generati</span><span class="sxs-lookup"><span data-stu-id="5921f-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="5921f-120">Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="5921f-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="5921f-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5921f-121">Click New.</span></span>
3. <span data-ttu-id="5921f-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5921f-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5921f-123">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5921f-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="5921f-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5921f-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5921f-125">Selezionare VendPay.</span><span class="sxs-lookup"><span data-stu-id="5921f-125">Select VendPay.</span></span>  
6. <span data-ttu-id="5921f-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5921f-126">Click Save.</span></span>
7. <span data-ttu-id="5921f-127">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="5921f-127">Click Lines.</span></span>
8. <span data-ttu-id="5921f-128">Digitare "DEMF" nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="5921f-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="5921f-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="5921f-129">DEMF</span></span>  
9. <span data-ttu-id="5921f-130">Nel campo Account, specificare i valori desiderati "DE-01001".</span><span class="sxs-lookup"><span data-stu-id="5921f-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="5921f-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="5921f-131">DE-01001</span></span>  
10. <span data-ttu-id="5921f-132">Digitare "Pagamento" nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="5921f-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="5921f-133">Pagamento</span><span class="sxs-lookup"><span data-stu-id="5921f-133">Payment</span></span>  
11. <span data-ttu-id="5921f-134">Nel campo Dare immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5921f-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="5921f-135">1000</span><span class="sxs-lookup"><span data-stu-id="5921f-135">1000</span></span>  
12. <span data-ttu-id="5921f-136">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="5921f-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="5921f-137">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5921f-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="5921f-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5921f-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5921f-139">Selezionare il valore elettronico.</span><span class="sxs-lookup"><span data-stu-id="5921f-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="5921f-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5921f-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="5921f-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5921f-141">Click Save.</span></span>
17. <span data-ttu-id="5921f-142">Fare clic su Genera pagamenti.</span><span class="sxs-lookup"><span data-stu-id="5921f-142">Click Generate payments.</span></span>
18. <span data-ttu-id="5921f-143">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5921f-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="5921f-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5921f-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5921f-145">Selezionare il valore elettronico.</span><span class="sxs-lookup"><span data-stu-id="5921f-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="5921f-146">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5921f-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5921f-147">Selezionare il valore elettronico.</span><span class="sxs-lookup"><span data-stu-id="5921f-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="5921f-148">Digitare un valore nel campo Nome file.</span><span class="sxs-lookup"><span data-stu-id="5921f-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="5921f-149">Ad esempio, digitare "pagamenti".</span><span class="sxs-lookup"><span data-stu-id="5921f-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="5921f-150">Nel campo Conto bancario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5921f-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="5921f-151">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5921f-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5921f-152">Selezionare il valore GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="5921f-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="5921f-153">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5921f-153">Click OK.</span></span>
25. <span data-ttu-id="5921f-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5921f-154">Click OK.</span></span>
    * <span data-ttu-id="5921f-155">Analizzare il file di pagamento creato in formato XML.</span><span class="sxs-lookup"><span data-stu-id="5921f-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="5921f-156">Confrontarlo con il layout del documento progettato e gli attributi di transazione del pagamento definiti.</span><span class="sxs-lookup"><span data-stu-id="5921f-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  

