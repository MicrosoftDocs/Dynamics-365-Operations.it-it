---
title: Creare un ordine fornitore da un ordine cliente
description: Questa procedura indica come creare un ordine fornitore in base a un ordine cliente.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7991476b86ace92cda513ae8906c62ba7fbbe915
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547424"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="35fbe-103">Creare un ordine fornitore da un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="35fbe-103">Create a purchase order from a sales order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="35fbe-104">Questa procedura indica come creare un ordine fornitore in base a un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-104">This procedure shows you how to create a purchase order that is based on a sales order.</span></span> <span data-ttu-id="35fbe-105">Le quantità del prodotto nell'ordine fornitore sono definite per soddisfare la richiesta dell'ordine cliente di origine.</span><span class="sxs-lookup"><span data-stu-id="35fbe-105">The product's quantities on the purchase order are then designated to fulfill the demand of the originating sales order.</span></span> <span data-ttu-id="35fbe-106">La richiesta di vendita soddisfatta in questo modo è un'alternativa all'approccio più completo e ottimizzato della pianificazione dei fabbisogni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="35fbe-106">Fulfilling sales demand this way is an alternative to a more comprehensive and optimized method of Distribution Requirements Planning.</span></span> <span data-ttu-id="35fbe-107">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="35fbe-107">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="35fbe-108">Creare un ordine fornitore da un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="35fbe-108">Create a purchase order from a sales order</span></span>
1. <span data-ttu-id="35fbe-109">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="35fbe-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="35fbe-110">Click New.</span></span>
3. <span data-ttu-id="35fbe-111">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="35fbe-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="35fbe-112">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="35fbe-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="35fbe-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="35fbe-113">Click OK.</span></span>
6. <span data-ttu-id="35fbe-114">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="35fbe-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="35fbe-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="35fbe-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35fbe-116">Se si utilizza USMF, è possibile selezionare D0001.</span><span class="sxs-lookup"><span data-stu-id="35fbe-116">If you're using USMF, you could select D0001.</span></span>  
8. <span data-ttu-id="35fbe-117">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="35fbe-117">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="35fbe-118">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="35fbe-118">Click Add line.</span></span>
10. <span data-ttu-id="35fbe-119">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="35fbe-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="35fbe-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="35fbe-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35fbe-121">Se si utilizza USMF, è possibile selezionare T0020.</span><span class="sxs-lookup"><span data-stu-id="35fbe-121">If you're using USMF, you could select T0020.</span></span>  
12. <span data-ttu-id="35fbe-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="35fbe-122">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="35fbe-123">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="35fbe-123">In the Quantity field, enter a number.</span></span>
14. <span data-ttu-id="35fbe-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="35fbe-124">Click Save.</span></span>
15. <span data-ttu-id="35fbe-125">Nel riquadro azioni fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-125">On the Action Pane, click Sales order.</span></span>
16. <span data-ttu-id="35fbe-126">Fare clic su Ordine acquisto.</span><span class="sxs-lookup"><span data-stu-id="35fbe-126">Click Purchase order.</span></span>
    * <span data-ttu-id="35fbe-127">Nella pagina Crea ordine acquisto è visualizzato l'elenco di tutte le righe ordine cliente aperte che sono state copiate dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-127">The Create purchase order page lists all the open sales order lines which have been copied from the sales order.</span></span> <span data-ttu-id="35fbe-128">È possibile esaminare i dettagli dell'ordine e se necessario, è possibile modificare i dettagli selezionati quali la quantità di acquisto e i termini per la determinazione del prezzo prima di creare gli acquisti.</span><span class="sxs-lookup"><span data-stu-id="35fbe-128">You can review the order details, and if required, you can modify selected details such purchase quantity and pricing terms, before you create the purchases.</span></span>  
17. <span data-ttu-id="35fbe-129">Selezionare l'opzione Includi tutto.</span><span class="sxs-lookup"><span data-stu-id="35fbe-129">Select the Include all option.</span></span>
    * <span data-ttu-id="35fbe-130">Se si desidera generare ordini acquisto solo per un sottoinsieme delle righe di ordine cliente, selezionarle singolarmente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-130">If you want to generate purchase orders for only a subset of the sales order lines, select these individually.</span></span>  
    * <span data-ttu-id="35fbe-131">Il campo Conto fornitore potrebbe essere già popolato con un numero fornitore.</span><span class="sxs-lookup"><span data-stu-id="35fbe-131">The Vendor account field may or may not already be populated with a vendor number.</span></span> <span data-ttu-id="35fbe-132">Se il fornitore predefinito è impostato per il prodotto (nella copertura articoli associata), questo fornitore verrà copiato nella riga.</span><span class="sxs-lookup"><span data-stu-id="35fbe-132">If the default vendor is set up for the product (on the associated Item coverage) then this vendor will be copied  to the line.</span></span> <span data-ttu-id="35fbe-133">In caso contrario, è necessario immettere manualmente un fornitore.</span><span class="sxs-lookup"><span data-stu-id="35fbe-133">Otherwise, you must enter a vendor manually.</span></span>  <span data-ttu-id="35fbe-134">Nella guida, indipendentemente dal campo Conto fornitore se già contiene un valore o meno, i seguenti passaggi indicano di selezionare un nuovo fornitore diverso per ciascuna riga.</span><span class="sxs-lookup"><span data-stu-id="35fbe-134">In this guide, regardless of whether the Vendor account field already contains a value or not, the following steps instruct you to select a new vendor which is different for each line.</span></span>  
18. <span data-ttu-id="35fbe-135">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="35fbe-135">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="35fbe-136">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="35fbe-136">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="35fbe-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="35fbe-137">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="35fbe-138">Selezionare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="35fbe-138">Select the second order line.</span></span>
22. <span data-ttu-id="35fbe-139">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="35fbe-139">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="35fbe-140">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="35fbe-140">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="35fbe-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="35fbe-141">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="35fbe-142">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="35fbe-142">Click Validate.</span></span>
26. <span data-ttu-id="35fbe-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="35fbe-143">Click OK.</span></span>
    * <span data-ttu-id="35fbe-144">Il messaggio informa che uno o più ordini acquisto non sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="35fbe-144">The message informs you that one or more purchase orders have been created.</span></span> <span data-ttu-id="35fbe-145">Il sistema genera un ordine acquisto separato per ciascun fornitore specificato per le righe dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-145">The system generates a separate purchase order for each vendor that you specified for the sales order lines.</span></span> <span data-ttu-id="35fbe-146">Pertanto se più righe di ordine cliente devono essere fornite dallo stesso fornitore, verrà generato un singolo ordine fornitore con più righe.</span><span class="sxs-lookup"><span data-stu-id="35fbe-146">This means that if several sales order lines are to be supplied by the same vendor, a single purchase order with multiple lines will be generated.</span></span>  

## <a name="review-purchase-orders-created-from-sales-orders"></a><span data-ttu-id="35fbe-147">Esaminare gli ordini acquisto creati da ordini cliente</span><span class="sxs-lookup"><span data-stu-id="35fbe-147">Review purchase orders created from sales orders</span></span>
1. <span data-ttu-id="35fbe-148">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="35fbe-148">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="35fbe-149">Fare clic su Ordini correlati.</span><span class="sxs-lookup"><span data-stu-id="35fbe-149">Click Related orders.</span></span>
    * <span data-ttu-id="35fbe-150">Nella pagina Ordini correlati sono elencati tutti gli ordini creati dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-150">The Related orders page lists all the orders that were created from the sales order.</span></span> <span data-ttu-id="35fbe-151">In questo esempio, sono disponibili due ordini fornitore generati per due fornitori diversi rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="35fbe-151">In this example, there are two purchase orders generated for two different vendors respectively.</span></span>  
3. <span data-ttu-id="35fbe-152">Fare clic per seguire il collegamento nel campo Ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="35fbe-152">Click to follow the link in the Purchase order field.</span></span>
    * <span data-ttu-id="35fbe-153">Ciascuna riga ordine fornitore è associata alla riga ordine cliente da cui ha avuto origine l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="35fbe-153">Each purchase order line is associated with the sales order line that led to the purchase.</span></span> <span data-ttu-id="35fbe-154">La relazione con l'ordine cliente viene visualizzata nella scheda Prodotto della scheda dettaglio Dettagli riga, nei campi Tipo di riferimento, Numero di riferimento e Lotto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="35fbe-154">The relation to the sales order is indicated on the Product tab in the Line details FastTab, in the Reference type, Reference number, and Reference lot fields.</span></span>  
4. <span data-ttu-id="35fbe-155">Espandere o comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="35fbe-155">Expand or collapse the Line details section.</span></span>
5. <span data-ttu-id="35fbe-156">Fare clic sulla scheda Prodotto.</span><span class="sxs-lookup"><span data-stu-id="35fbe-156">Click the Product tab.</span></span>
    * <span data-ttu-id="35fbe-157">Il lotto di riferimento garantisce che i costi dell'acquisto corrente vengano addebitati all'ordine cliente collegato.</span><span class="sxs-lookup"><span data-stu-id="35fbe-157">The Reference lot guarantees that the costs from the current purchase are charged on the attached sales order.</span></span>  
    * <span data-ttu-id="35fbe-158">È possibile passare all'ordine cliente di origine aprendo il collegamento nel campo Numero di riferimento.</span><span class="sxs-lookup"><span data-stu-id="35fbe-158">You can navigate to the originating sales order by opening the link in the Reference number field.</span></span>  

