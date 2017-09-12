--- 
title: Registrare le provvigioni di vendita
description: Questa procedura mostra come le provvigioni di vendita vengono calcolate e registrate.
author: omulvad
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
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f195f9e466eab3cf87afea2b5d430d0ea25c5a83
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="register-sales-commissions"></a><span data-ttu-id="9ee53-103">Registrare le provvigioni di vendita</span><span class="sxs-lookup"><span data-stu-id="9ee53-103">Register sales commissions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9ee53-104">Questa procedura mostra come le provvigioni di vendita vengono calcolate e registrate.</span><span class="sxs-lookup"><span data-stu-id="9ee53-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="9ee53-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="9ee53-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="9ee53-106">Prima di iniziare questa guida, eseguire la guida chiamata “Impostare regole per la provvigione vendite" per assicurarsi che tutto il necessario per il calcolo della provvigione sia impostato.</span><span class="sxs-lookup"><span data-stu-id="9ee53-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="9ee53-107">Prendere nota dei numeri cliente e articolo scelti per il processo di provvigione e usarli quando chiesto per creare un ordine cliente nella guida.</span><span class="sxs-lookup"><span data-stu-id="9ee53-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="9ee53-108">Fatturare un ordine cliente che qualifica un venditore per una provvigione</span><span class="sxs-lookup"><span data-stu-id="9ee53-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="9ee53-109">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="9ee53-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="9ee53-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9ee53-110">Click New.</span></span>
3. <span data-ttu-id="9ee53-111">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9ee53-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9ee53-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="9ee53-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="9ee53-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9ee53-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="9ee53-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9ee53-114">Click OK.</span></span>
7. <span data-ttu-id="9ee53-115">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="9ee53-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="9ee53-116">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-116">Click Change view.</span></span>
9. <span data-ttu-id="9ee53-117">Fare clic su Visualizzazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-117">Click Header view.</span></span>
10. <span data-ttu-id="9ee53-118">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="9ee53-119">Il valore nel campo Gruppo vendite rappresenta un gruppo a cui sono assegnati uno o più rappresentanti.</span><span class="sxs-lookup"><span data-stu-id="9ee53-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="9ee53-120">Le persone nel gruppo sono quelle che ricevono le provvigioni quando l'ordine viene fatturato, secondo le percentuali e la distribuzione predefinite.</span><span class="sxs-lookup"><span data-stu-id="9ee53-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="9ee53-121">Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.</span><span class="sxs-lookup"><span data-stu-id="9ee53-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="9ee53-122">Il gruppo vendite verrà copiato anche nella riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9ee53-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="9ee53-123">È possibile modificarlo in modo che sia diverso da quello nell'intestazione e/o tra le righe.</span><span class="sxs-lookup"><span data-stu-id="9ee53-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="9ee53-124">Il valore nel campo Gruppo provvigioni rappresenta un gruppo creato per uno o più clienti a scopo di tracciabilità delle provvigioni.</span><span class="sxs-lookup"><span data-stu-id="9ee53-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="9ee53-125">Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.</span><span class="sxs-lookup"><span data-stu-id="9ee53-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="9ee53-126">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="9ee53-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="9ee53-127">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-127">Click Change view.</span></span>
13. <span data-ttu-id="9ee53-128">Fare clic su Visualizzazione riga.</span><span class="sxs-lookup"><span data-stu-id="9ee53-128">Click Line view.</span></span>
14. <span data-ttu-id="9ee53-129">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9ee53-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="9ee53-130">Nell'elenco, selezionare l'articolo impostato per le provvigioni.</span><span class="sxs-lookup"><span data-stu-id="9ee53-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="9ee53-131">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="9ee53-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="9ee53-132">Prendere nota dell'importo netto della riga.</span><span class="sxs-lookup"><span data-stu-id="9ee53-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="9ee53-133">Rappresenta i ricavi di vendita, che in questo esempio costituiscono la base per il calcolo della provvigione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="9ee53-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9ee53-134">Click Save.</span></span>
18. <span data-ttu-id="9ee53-135">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="9ee53-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="9ee53-136">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="9ee53-136">Click Invoice.</span></span>
20. <span data-ttu-id="9ee53-137">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="9ee53-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="9ee53-138">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="9ee53-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="9ee53-139">Selezionare Sì nel campo Registrazione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="9ee53-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9ee53-140">Click OK.</span></span>
24. <span data-ttu-id="9ee53-141">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9ee53-141">Click OK.</span></span>
    * <span data-ttu-id="9ee53-142">Può richiedere qualche minuto registrare la transazione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="9ee53-143">Attendere il completamento dell'elaborazione e non chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9ee53-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="9ee53-144">Verificare le provvigioni vendite registrate</span><span class="sxs-lookup"><span data-stu-id="9ee53-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="9ee53-145">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="9ee53-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="9ee53-146">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="9ee53-146">Click Invoice.</span></span>
3. <span data-ttu-id="9ee53-147">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="9ee53-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="9ee53-148">Fare clic su Transazioni provvigione.</span><span class="sxs-lookup"><span data-stu-id="9ee53-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="9ee53-149">La scheda Panoramica visualizza le righe che rappresentano gli importi di provvigione dovuti ai rappresentanti associati all'ordine cliente fatturato.</span><span class="sxs-lookup"><span data-stu-id="9ee53-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="9ee53-150">Esaminiamo i dettagli.</span><span class="sxs-lookup"><span data-stu-id="9ee53-150">Let's review the details.</span></span>     
    * <span data-ttu-id="9ee53-151">Se è stata utilizzata la guida "Impostare regole per la provvigione vendite" per impostare il gruppo vendite con provvigione, sono presenti due venditori per ricevere le provvigioni di vendita e la provvigione è divisa equamente tra loro.</span><span class="sxs-lookup"><span data-stu-id="9ee53-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="9ee53-152">In questo esempio, l'importo totale delle provvigioni viene calcolato come percentuale di ricavi da vendite (l'importo netto della riga ordine).</span><span class="sxs-lookup"><span data-stu-id="9ee53-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="9ee53-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9ee53-153">Close the page.</span></span>
6. <span data-ttu-id="9ee53-154">Fare clic su Giustificativo.</span><span class="sxs-lookup"><span data-stu-id="9ee53-154">Click Voucher.</span></span>
    * <span data-ttu-id="9ee53-155">È possibile esaminare le transazioni giustificativo per gli importi della provvigione registrati nei conti predefiniti Commissioni e Importo a debito provvigioni.</span><span class="sxs-lookup"><span data-stu-id="9ee53-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


