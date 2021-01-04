---
title: Registrare l'entrata di merci sull'ordine fornitore
description: Questa argomento descrive come registrare l'entrata delle merci direttamente su un ordine fornitore.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd8ca2cbd24f326c4eaf9cd39e32de0eca81149d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431576"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="3ee2a-103">Registrare l'entrata di merci sull'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="3ee2a-103">Record the receipt of goods on the purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ee2a-104">Questa argomento descrive come registrare l'entrata delle merci direttamente su un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-104">This topic explains how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="3ee2a-105">È inoltre possibile registrare l'entrata prodotti nel magazzino e poi registrarla successivamente sull'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-105">It's also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="3ee2a-106">Quest'attività viene eseguita tipicamente da un addetto acquisti o un coordinatore contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="3ee2a-107">L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="3ee2a-108">L'esempio comprende i passaggi per creare un ordine fornitore semplice in modo da poter eseguire la procedura come guida attività.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="3ee2a-109">Se si seguisse la procedura utilizzando i propri dati, si dovrebbe iniziare con la sottoattività **Registrare l'entrata dei prodotti**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-109">If you were using the procedure on your own data, you would start at the **Record receipt of goods** subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="3ee2a-110">Preparare un nuovo ordine fornitore per l'entrata delle merci</span><span class="sxs-lookup"><span data-stu-id="3ee2a-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="3ee2a-111">Passare a **pannello di navigazione > Moduli > Approvvigionamento > Ordini fornitore > Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-111">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="3ee2a-112">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-112">Select **New**.</span></span>
3. <span data-ttu-id="3ee2a-113">Nel campo **Conto fornitore** immettere `US-101`.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-113">In the **Vendor account** field, enter `US-101`.</span></span>
4. <span data-ttu-id="3ee2a-114">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-114">Select **OK**.</span></span>
5. <span data-ttu-id="3ee2a-115">Nel campo **Numero articolo** immettere `M0001`.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-115">In the **Item number** field, enter `M0001`.</span></span>
6. <span data-ttu-id="3ee2a-116">Nel campo **Quantità** immettere `5`.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-116">In the **Quantity** field, enter `5`.</span></span>
7. <span data-ttu-id="3ee2a-117">Nel riquadro azioni fare clic su **Acquisto**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-117">On the Action Pane, select **Purchase**.</span></span>
8. <span data-ttu-id="3ee2a-118">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-118">Select **Confirm**.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="3ee2a-119">Registrare l'entrata dei prodotti</span><span class="sxs-lookup"><span data-stu-id="3ee2a-119">Record receipt of goods</span></span>
1. <span data-ttu-id="3ee2a-120">Nel riquadro azioni fare clic su **Ricevimento**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-120">On the Action Pane, select **Receive**.</span></span>
2. <span data-ttu-id="3ee2a-121">Selezionare **Entrata prodotti**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-121">Select **Product receipt**.</span></span> <span data-ttu-id="3ee2a-122">Il campo **Quantità** permette di selezionare opzioni differenti per la quantità che volete ricevere.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-122">The **Quantity** field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="3ee2a-123">Ad esempio, se una quantità precedentemente è stata registrata nel magazzino, potete selezionare **Quantità registrata**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-123">For example, if a quantity has previously been registered in the warehouse, you can select **Registered quantity**.</span></span> <span data-ttu-id="3ee2a-124">Per questo esempio, usare il valore **Quantità ordinata**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-124">For this example, use the value **Ordered quantity**.</span></span>
3. <span data-ttu-id="3ee2a-125">Espandere la sezione **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-125">Expand the **Overview** section.</span></span>
4. <span data-ttu-id="3ee2a-126">Digitare un valore nel campo **Entrata prodotti**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-126">In the **Product receipt** field, type any value.</span></span> <span data-ttu-id="3ee2a-127">Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-127">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
5. <span data-ttu-id="3ee2a-128">Espandere la sezione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-128">Expand the **Lines** section.</span></span>
6. <span data-ttu-id="3ee2a-129">Impostare **Quantità** su '4'.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-129">Set **Quantity** to '4'.</span></span> <span data-ttu-id="3ee2a-130">Qui potete specificare manualmente la quantità che si sta ricevendo per ogni riga sull'ordine.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-130">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
7. <span data-ttu-id="3ee2a-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-131">Select **OK**.</span></span> <span data-ttu-id="3ee2a-132">Le merci ora sono state registrate come ricevute sull'ordine fornitore e un giornale di registrazione entrata prodotti è stato creato come documento per riflettere questo.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="3ee2a-133">Potete usare l'azione Entrata prodotti per esaminare i giornali di registrazione creati con l'ordine fornitore e vedere che cosa è stato ricevuto e quando.</span><span class="sxs-lookup"><span data-stu-id="3ee2a-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  

