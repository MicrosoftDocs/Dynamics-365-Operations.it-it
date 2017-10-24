--- 
title: Rilasciare un certificato di entrata UE
description: Questa procedura consente di abilitare un certificato di entrata UE, configurando un conto cliente per utilizzare i certificati di entrata e rilasciare un certificato.
author: mrolecki
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ff00ff0df3835ee2cbf21219ad6f07bfeba6e7ac
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="issue-an-eu-entry-certificate"></a><span data-ttu-id="a97c1-103">Rilasciare un certificato di entrata UE</span><span class="sxs-lookup"><span data-stu-id="a97c1-103">Issue an EU entry certificate</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a97c1-104">Questa procedura consente di abilitare un certificato di entrata UE, configurando un conto cliente per utilizzare i certificati di entrata e rilasciare un certificato.</span><span class="sxs-lookup"><span data-stu-id="a97c1-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="a97c1-105">Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="a97c1-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="a97c1-106">Abilita gestione certificati di entrata</span><span class="sxs-lookup"><span data-stu-id="a97c1-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="a97c1-107">Andare a a Contabilità clienti > Impostazioni > Parametri contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="a97c1-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="a97c1-108">Fare clic sulla scheda Spedizioni.</span><span class="sxs-lookup"><span data-stu-id="a97c1-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="a97c1-109">Espandere la sezione Certificato di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="a97c1-110">Selezionare Sì nel campo Abilita gestione certificati di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="a97c1-111">Selezionare Sì nel campo Abilita rilascio certificato di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="a97c1-112">Fare clic sulla scheda Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="a97c1-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="a97c1-113">Nell'elenco trovare e selezionare la riga Certificato di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="a97c1-114">Nel campo Codice sequenza numerica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a97c1-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="a97c1-115">Impostare un cliente</span><span class="sxs-lookup"><span data-stu-id="a97c1-115">Set up a customer</span></span>
1. <span data-ttu-id="a97c1-116">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="a97c1-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="a97c1-117">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="a97c1-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a97c1-118">Ad esempio, filtrare nel campo Conto con un valore "DE-015".</span><span class="sxs-lookup"><span data-stu-id="a97c1-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="a97c1-119">Aprire i dettagli del conto cliente.</span><span class="sxs-lookup"><span data-stu-id="a97c1-119">Open customer account details.</span></span>
4. <span data-ttu-id="a97c1-120">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a97c1-120">Click Edit.</span></span>
5. <span data-ttu-id="a97c1-121">Espandere la sezione Fattura e consegna.</span><span class="sxs-lookup"><span data-stu-id="a97c1-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="a97c1-122">Selezionare Sì nel campo Certificato di entrata obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a97c1-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="a97c1-123">Selezionare Sì nel campo Rilascia certificato di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="a97c1-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a97c1-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="a97c1-125">Creare automaticamente un certificato di entrata UE</span><span class="sxs-lookup"><span data-stu-id="a97c1-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="a97c1-126">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="a97c1-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a97c1-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a97c1-127">Click New.</span></span>
3. <span data-ttu-id="a97c1-128">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a97c1-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="a97c1-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-129">Click OK.</span></span>
5. <span data-ttu-id="a97c1-130">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a97c1-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="a97c1-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a97c1-131">Click Save.</span></span>
7. <span data-ttu-id="a97c1-132">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="a97c1-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="a97c1-133">Fare clic su Registra documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a97c1-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="a97c1-134">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="a97c1-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="a97c1-135">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="a97c1-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="a97c1-136">Deselezionare la casella di controllo Rilascia certificato di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="a97c1-137">Un certificato di entrata può essere rilasciato durante la registrazione del documento di trasporto o durante la fatturazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="a97c1-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="a97c1-138">Lasciare la casella di controllo Rilascia certificato di entrata deselezionata per rilasciarlo successivamente.</span><span class="sxs-lookup"><span data-stu-id="a97c1-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="a97c1-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-139">Click OK.</span></span>
13. <span data-ttu-id="a97c1-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-140">Click OK.</span></span>
14. <span data-ttu-id="a97c1-141">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="a97c1-142">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-142">Click Invoice.</span></span>
    * <span data-ttu-id="a97c1-143">Verificare che le caselle di controllo Certificato di entrata obbligatorio e Rilascia certificato di entrata nella sezione Panoramica siano selezionate.</span><span class="sxs-lookup"><span data-stu-id="a97c1-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="a97c1-144">È inoltre possibile selezionare la casella di controllo Stampa certificato di entrata per consentire la stampa del certificato.</span><span class="sxs-lookup"><span data-stu-id="a97c1-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="a97c1-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-145">Click OK.</span></span>
17. <span data-ttu-id="a97c1-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-146">Click OK.</span></span>
18. <span data-ttu-id="a97c1-147">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="a97c1-148">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-148">Click Invoice.</span></span>
20. <span data-ttu-id="a97c1-149">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="a97c1-150">Fare clic su Visualizza certificati di entrata rilasciati.</span><span class="sxs-lookup"><span data-stu-id="a97c1-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="a97c1-151">Fare clic su Stampa.</span><span class="sxs-lookup"><span data-stu-id="a97c1-151">Click Print.</span></span>
23. <span data-ttu-id="a97c1-152">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a97c1-152">Close the page.</span></span>
24. <span data-ttu-id="a97c1-153">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="a97c1-153">Click Change status.</span></span>
25. <span data-ttu-id="a97c1-154">Selezionare un'opzione nel campo Nuovo stato.</span><span class="sxs-lookup"><span data-stu-id="a97c1-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="a97c1-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-155">Click OK.</span></span>
27. <span data-ttu-id="a97c1-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a97c1-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="a97c1-157">Creare manualmente un certificato di entrata UE</span><span class="sxs-lookup"><span data-stu-id="a97c1-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="a97c1-158">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="a97c1-159">Fare clic su Crea certificato di entrata.</span><span class="sxs-lookup"><span data-stu-id="a97c1-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="a97c1-160">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a97c1-160">Click OK.</span></span>
4. <span data-ttu-id="a97c1-161">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="a97c1-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="a97c1-162">Fare clic su Visualizza certificati di entrata rilasciati.</span><span class="sxs-lookup"><span data-stu-id="a97c1-162">Click View issued entry certificates.</span></span>


