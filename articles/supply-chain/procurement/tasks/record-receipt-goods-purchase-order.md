--- 
title: Registrare l'entrata di merci sull'ordine fornitore
description: Questa procedura mostra come registrare l'entrata delle merci direttamente su un ordine fornitore.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a9c87b8790ed6cfe4139180f1f1785db04e7431
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="9f241-103">Registrare l'entrata di merci sull'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="9f241-103">Record the receipt of goods on the purchase order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f241-104">Questa procedura mostra come registrare l'entrata delle merci direttamente su un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="9f241-104">This procedure shows you how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="9f241-105">È inoltre possibile registrare l'entrata prodotti nel magazzino e poi registrarla successivamente sull'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="9f241-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="9f241-106">Quest'attività viene eseguita tipicamente da un addetto acquisti o un coordinatore contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="9f241-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="9f241-107">L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="9f241-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="9f241-108">L'esempio comprende i passaggi per creare un ordine fornitore semplice in modo da poter eseguire la procedura come guida attività.</span><span class="sxs-lookup"><span data-stu-id="9f241-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="9f241-109">Se si seguisse la procedura utilizzando i propri dati, si dovrebbe iniziare con la sottoattività Registrare l'entrata dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="9f241-109">If you were using the procedure on your own data, you would start at the Record receipt of goods subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="9f241-110">Preparare un nuovo ordine fornitore per l'entrata delle merci</span><span class="sxs-lookup"><span data-stu-id="9f241-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="9f241-111">Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="9f241-111">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="9f241-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f241-112">Click New.</span></span>
3. <span data-ttu-id="9f241-113">Digitare US-101 nel campo Conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="9f241-113">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="9f241-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9f241-114">Click OK.</span></span>
5. <span data-ttu-id="9f241-115">Nel campo Numero articolo immettere M0001.</span><span class="sxs-lookup"><span data-stu-id="9f241-115">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="9f241-116">Nel campo Quantità immettere 5.</span><span class="sxs-lookup"><span data-stu-id="9f241-116">In the Quantity field, enter 5.</span></span>
7. <span data-ttu-id="9f241-117">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="9f241-117">On the Action Pane, click Purchase.</span></span>
8. <span data-ttu-id="9f241-118">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="9f241-118">Click Confirm.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="9f241-119">Registrare l'entrata dei prodotti</span><span class="sxs-lookup"><span data-stu-id="9f241-119">Record receipt of goods</span></span>
1. <span data-ttu-id="9f241-120">Nel riquadro azioni fare clic su Ricevimento.</span><span class="sxs-lookup"><span data-stu-id="9f241-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="9f241-121">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="9f241-121">Click Product receipt.</span></span>
    * <span data-ttu-id="9f241-122">Il campo Quantità permette di selezionare opzioni differenti per la quantità che volete ricevere.</span><span class="sxs-lookup"><span data-stu-id="9f241-122">The Quantity field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="9f241-123">Ad esempio, se una quantità precedentemente è stata registrata nel magazzino, potete selezionare Quantità registrata.</span><span class="sxs-lookup"><span data-stu-id="9f241-123">For example, if a quantity has previously been registered in the warehouse, you can select Registered quantity.</span></span>  <span data-ttu-id="9f241-124">Per questo esempio, usare il valore Quantità ordinata.</span><span class="sxs-lookup"><span data-stu-id="9f241-124">For this example, use the value Ordered quantity.</span></span>   
3. <span data-ttu-id="9f241-125">Digitare un valore nel campo Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="9f241-125">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="9f241-126">Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="9f241-126">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
4. <span data-ttu-id="9f241-127">Espandere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="9f241-127">Expand the Lines section.</span></span>
5. <span data-ttu-id="9f241-128">Impostare la quantità su "4".</span><span class="sxs-lookup"><span data-stu-id="9f241-128">Set Quantity to '4'.</span></span>
    * <span data-ttu-id="9f241-129">Qui potete specificare manualmente la quantità che si sta ricevendo per ogni riga sull'ordine.</span><span class="sxs-lookup"><span data-stu-id="9f241-129">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
6. <span data-ttu-id="9f241-130">Comprimere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="9f241-130">Collapse the Lines section.</span></span>
7. <span data-ttu-id="9f241-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9f241-131">Click OK.</span></span>
    * <span data-ttu-id="9f241-132">Le merci ora sono state registrate come ricevute sull'ordine fornitore e un giornale di registrazione entrata prodotti è stato creato come documento per riflettere questo.</span><span class="sxs-lookup"><span data-stu-id="9f241-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="9f241-133">Potete usare l'azione Entrata prodotti per esaminare i giornali di registrazione creati con l'ordine fornitore e vedere che cosa è stato ricevuto e quando.</span><span class="sxs-lookup"><span data-stu-id="9f241-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  


