--- 
title: Gestire sospensioni ordine
description: In questa procedura viene illustrato come mettere in sospeso ordini cliente, come utilizzare i check-out della sospensioni ordine e come rimuovere le sospensioni ordine.
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 5e51cd1245c578762791e7fe023c36e6fd779086
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="manage-order-holds"></a><span data-ttu-id="754f2-103">Gestire sospensioni ordine</span><span class="sxs-lookup"><span data-stu-id="754f2-103">Manage order holds</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="754f2-104">In questa procedura viene illustrato come mettere in sospeso ordini cliente, come utilizzare i check-out della sospensioni ordine e come rimuovere le sospensioni ordine.</span><span class="sxs-lookup"><span data-stu-id="754f2-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="754f2-105">Un ordine può essere sospeso per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="754f2-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="754f2-106">Ad esempio, è possibile sospendere un ordine fino a che non può essere verificato un indirizzo cliente o un metodo di pagamento o fino a che un responsabile può verificare il limite di credito del cliente.</span><span class="sxs-lookup"><span data-stu-id="754f2-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="754f2-107">Quando l'ordine è in sospeso, non potrà essere elaborato dal magazzino per la spedizione.</span><span class="sxs-lookup"><span data-stu-id="754f2-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="754f2-108">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="754f2-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="754f2-109">Impostare sospensioni ordine</span><span class="sxs-lookup"><span data-stu-id="754f2-109">Set up order holds</span></span>
1. <span data-ttu-id="754f2-110">Passare a Vendite e marketing > Impostazioni > Ordini cliente > Codici sospensione ordine.</span><span class="sxs-lookup"><span data-stu-id="754f2-110">Go to Sales and marketing > Setup > Sales orders > Order hold codes.</span></span>
2. <span data-ttu-id="754f2-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="754f2-111">Click New.</span></span>
3. <span data-ttu-id="754f2-112">Digitare un valore nel campo Codice sospensione.</span><span class="sxs-lookup"><span data-stu-id="754f2-112">In the Hold code field, type a value.</span></span>
    * <span data-ttu-id="754f2-113">Ad esempio, digitare Richiamata.</span><span class="sxs-lookup"><span data-stu-id="754f2-113">For example, type Call back.</span></span>  
4. <span data-ttu-id="754f2-114">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="754f2-114">In the Description field, type a value.</span></span>
    * <span data-ttu-id="754f2-115">Ad esempio, ordine in sospeso in attesa il contenuto del cliente.</span><span class="sxs-lookup"><span data-stu-id="754f2-115">For example, Order held waiting for customer callback.</span></span>  
    * <span data-ttu-id="754f2-116">Facoltativamente, selezionare la casella di controllo Rimuovi prenotazioni per rimuovere tutte le prenotazioni fisiche dall'ordine quando il codice di sospensione viene aggiunto.</span><span class="sxs-lookup"><span data-stu-id="754f2-116">Optionally, select the Remove reservations check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="754f2-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="754f2-117">Click Save.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="754f2-118">Mettere un ordine in attesa</span><span class="sxs-lookup"><span data-stu-id="754f2-118">Place order on hold</span></span>
1. <span data-ttu-id="754f2-119">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="754f2-119">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="754f2-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="754f2-120">Click New.</span></span>
3. <span data-ttu-id="754f2-121">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="754f2-121">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="754f2-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="754f2-122">Click OK.</span></span>
5. <span data-ttu-id="754f2-123">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="754f2-123">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="754f2-124">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="754f2-124">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="754f2-125">Nel riquadro azioni fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="754f2-125">On the Action Pane, click Sales order.</span></span>
8. <span data-ttu-id="754f2-126">Fare clic su Sospensioni ordine.</span><span class="sxs-lookup"><span data-stu-id="754f2-126">Click Order holds.</span></span>
9. <span data-ttu-id="754f2-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="754f2-127">Click New.</span></span>
10. <span data-ttu-id="754f2-128">Nel campo Codice sospensione, selezionare il codice creato nella sottoattività precedente.</span><span class="sxs-lookup"><span data-stu-id="754f2-128">In the Hold code field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="754f2-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="754f2-129">Click Save.</span></span>
12. <span data-ttu-id="754f2-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="754f2-130">Close the page.</span></span>
13. <span data-ttu-id="754f2-131">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="754f2-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
14. <span data-ttu-id="754f2-132">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="754f2-132">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="754f2-133">Gli ordini attualmente in attesa hanno i campi "Non elaborare"e "Pausa" contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="754f2-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>    
15. <span data-ttu-id="754f2-134">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="754f2-134">On the Action Pane, click Pick and pack.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="754f2-135">Gestire sospensioni ordine</span><span class="sxs-lookup"><span data-stu-id="754f2-135">Manage order holds</span></span>
1. <span data-ttu-id="754f2-136">Passare a Vendite e marketing > Ordini cliente > Ordini aperti > Sospensioni ordine.</span><span class="sxs-lookup"><span data-stu-id="754f2-136">Go to Sales and marketing > Sales orders > Open orders > Order holds.</span></span>
    * <span data-ttu-id="754f2-137">La pagina delle sospensioni ordini funziona come workbench in cui è possibile visualizzare una panoramica di tutte le sospensioni correnti ed elaborate e gestire le sospensioni e gli ordini cliente associati.</span><span class="sxs-lookup"><span data-stu-id="754f2-137">Order holds page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>      
2. <span data-ttu-id="754f2-138">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="754f2-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="754f2-139">Nel riquadro azioni, fare clic su Sospendi estrazione.</span><span class="sxs-lookup"><span data-stu-id="754f2-139">On the Action Pane, click Hold checkout.</span></span>
4. <span data-ttu-id="754f2-140">Fare clic su Estrai.</span><span class="sxs-lookup"><span data-stu-id="754f2-140">Click Check out.</span></span>
5. <span data-ttu-id="754f2-141">Nell'elenco deselezionare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="754f2-141">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="754f2-142">Il campo Estrai in ora mostra l'ID utente.</span><span class="sxs-lookup"><span data-stu-id="754f2-142">The Checkout out to field now shows your user ID.</span></span>   
6. <span data-ttu-id="754f2-143">Fare clic su Cancella estrazione.</span><span class="sxs-lookup"><span data-stu-id="754f2-143">Click Clear checkout.</span></span>
7. <span data-ttu-id="754f2-144">Nel riquadro azioni, fare clic su Cancella sospensione.</span><span class="sxs-lookup"><span data-stu-id="754f2-144">On the Action Pane, click Clear hold.</span></span>
    * <span data-ttu-id="754f2-145">Quando si è pronti a rimuovere la sospensione e a consentire all'ordine di procedere al passaggio successivo dell'evasione, è necessario cancellare la sospensione.</span><span class="sxs-lookup"><span data-stu-id="754f2-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="754f2-146">Se per l'ordine non sono necessarie modifiche, è possibile eseguire l'azione Cancella sospensioni.</span><span class="sxs-lookup"><span data-stu-id="754f2-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="754f2-147">Tuttavia, è possibile utilizzare l'azione Cancella e modifica, se al momento della cancellazione di una sospensione, l'ordine deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="754f2-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    * <span data-ttu-id="754f2-148">L'azione Cancella e invia è applicabile solo quando si utilizza la funzionalità Servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="754f2-148">The Clear and submit action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="754f2-149">Fare clic su Cancella sospensioni.</span><span class="sxs-lookup"><span data-stu-id="754f2-149">Click Clear holds.</span></span>
    * <span data-ttu-id="754f2-150">La sospensione è stata cancellata dall'ordine e rimossa dall'elenco delle sospensioni attive.</span><span class="sxs-lookup"><span data-stu-id="754f2-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="754f2-151">Per visualizzare tutte le sospensioni o i relativi sottoinsiemi in base a uno stato specifico, modificare il valore nel campo Mostra.</span><span class="sxs-lookup"><span data-stu-id="754f2-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     


