---
title: Eseguire il prezzo di costo e restituire l'ID lotto
description: Si può decidere che il costo dei prodotti resi deve essere uguale al costo dei prodotti nel momento in cui sono stati venduti al cliente. È possibile effettuare questa operazione utilizzando **Operazione ID lotto**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eff30383e06677793313e8abac0339c6032c2a7f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965832"
---
# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="47c41-104">Eseguire il prezzo di costo e restituire l'ID lotto</span><span class="sxs-lookup"><span data-stu-id="47c41-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="47c41-105">Il costo dei prodotti resi al magazzino viene calcolato utilizzando il costo corrente dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="47c41-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="47c41-106">Si può tuttavia decidere che il costo dei prodotti resi deve essere uguale al costo dei prodotti nel momento in cui sono stati venduti al cliente.</span><span class="sxs-lookup"><span data-stu-id="47c41-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="47c41-107">A tale scopo, utilizzare il campo **ID lotto resi** della Scheda dettaglio **Dettagli riga** nel modulo **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="47c41-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="47c41-108">Ad esempio, considerare il seguente scenario.</span><span class="sxs-lookup"><span data-stu-id="47c41-108">For example, consider the following scenario.</span></span> <span data-ttu-id="47c41-109">Si invia la fattura a un cliente.</span><span class="sxs-lookup"><span data-stu-id="47c41-109">You invoice a customer.</span></span> <span data-ttu-id="47c41-110">Quindi, il cliente restituisce i prodotti consegnati.</span><span class="sxs-lookup"><span data-stu-id="47c41-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="47c41-111">I prodotti vengono restituiti al magazzino.</span><span class="sxs-lookup"><span data-stu-id="47c41-111">You return the products to stock.</span></span> <span data-ttu-id="47c41-112">In questo caso, quando si emette una nota di accredito al cliente per i prodotti resi, il costo dei prodotti viene calcolato utilizzando il costo corrente dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="47c41-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="47c41-113">Se invece si utilizza il campo **ID lotto resi**, il costo dei prodotti resi viene calcolato utilizzando il costo riportato nella fattura di vendita originale al cliente.</span><span class="sxs-lookup"><span data-stu-id="47c41-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="47c41-114">Per utilizzare un costo diverso da quello corrente per i resi da un cliente, utilizzare uno dei seguenti metodi.</span><span class="sxs-lookup"><span data-stu-id="47c41-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="47c41-115">Metodo 1: immettere manualmente il prezzo di costo di reso</span><span class="sxs-lookup"><span data-stu-id="47c41-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="47c41-116">Per impostazione predefinita, quando si aggiungono articoli a un ordine di reso, gli articoli vengono restituiti al magazzino al prezzo di costo corrente.</span><span class="sxs-lookup"><span data-stu-id="47c41-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="47c41-117">Per specificare un prezzo di costo di reso diverso, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="47c41-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="47c41-118">Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.</span><span class="sxs-lookup"><span data-stu-id="47c41-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="47c41-119">Nel **riquadro azioni** fare clic su **Ordine di reso** nel gruppo **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="47c41-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="47c41-120">Nel modulo **Crea ordine di reso**, selezionare un conto cliente e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47c41-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="47c41-121">Nel modulo **Ordine di reso - Codice NAR: %1, %2**, selezionare un articolo e immettere una quantità negativa nel campo **Quantità**.</span><span class="sxs-lookup"><span data-stu-id="47c41-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="47c41-122">Fare clic sulla Scheda dettaglio **Dettagli riga**.</span><span class="sxs-lookup"><span data-stu-id="47c41-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="47c41-123">Nella scheda **Generale** immettere un valore nel campo **Prezzo di costo reso**.</span><span class="sxs-lookup"><span data-stu-id="47c41-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="47c41-124">Questo valore viene utilizzato quando le merci vengono restituite al magazzino.</span><span class="sxs-lookup"><span data-stu-id="47c41-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="47c41-125">Se non si immette alcun valore, il prezzo di costo corrente viene utilizzato quando le merci vengono restituite al magazzino.</span><span class="sxs-lookup"><span data-stu-id="47c41-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="47c41-126">Metodo 2: generare automaticamente il prezzo di costo in base alla riga fattura cliente</span><span class="sxs-lookup"><span data-stu-id="47c41-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="47c41-127">Questo è il metodo preferito da utilizzare per creare le righe di reso.</span><span class="sxs-lookup"><span data-stu-id="47c41-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="47c41-128">Per utilizzare il costo dei prodotti nel momento in cui sono stati venduti al cliente, creare un ordine di reso e specificare una riga di vendita da restituire.</span><span class="sxs-lookup"><span data-stu-id="47c41-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="47c41-129">Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.</span><span class="sxs-lookup"><span data-stu-id="47c41-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="47c41-130">Nel **riquadro azioni** fare clic su **Ordine di reso** nel gruppo **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="47c41-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="47c41-131">Nel modulo **Crea ordine di reso**, selezionare un conto cliente e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47c41-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="47c41-132">Nel modulo **Ordine di reso - Codice NAR: %1, %2** nel **riquadro azioni**, fare clic su **Trova ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="47c41-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="47c41-133">Nel modulo **Trova ordine cliente** selezionare la riga fattura per il reso, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47c41-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="47c41-134">Nella Scheda dettaglio **Dettagli riga**, nella scheda **Generale**, il campo **ID lotto resi** visualizza il valore della riga di vendita originale.</span><span class="sxs-lookup"><span data-stu-id="47c41-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="47c41-135">Inoltre, il campo **Prezzo di costo reso** visualizza il valore di costo dalla riga di vendita originale.</span><span class="sxs-lookup"><span data-stu-id="47c41-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="47c41-136">Esempio di calcolo dei costi</span><span class="sxs-lookup"><span data-stu-id="47c41-136">Cost calculation example</span></span>

<span data-ttu-id="47c41-137">Quando si utilizza il campo **ID lotto resi** in una riga ordine di reso per specificare il prezzo di costo di reso, viene utilizzato il costo nella riga ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="47c41-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="47c41-138">Se si esegue la funzionalità di chiusura o il ricalcolo di inventario, il costo viene rettificato nella riga di vendita originale.</span><span class="sxs-lookup"><span data-stu-id="47c41-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="47c41-139">Il costo nella riga ordine di reso viene rettificato automaticamente per riflettere lo stesso costo per pezzo.</span><span class="sxs-lookup"><span data-stu-id="47c41-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="47c41-140">Creare e rilasciare un prodotto denominato Test.</span><span class="sxs-lookup"><span data-stu-id="47c41-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="47c41-141">Nel modulo **Dettagli prodotto rilasciato**, specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47c41-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="47c41-142">Nella Scheda dettaglio **Gestisci costi** selezionare il gruppo **Parti** nel campo **Gruppo di articoli**.</span><span class="sxs-lookup"><span data-stu-id="47c41-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="47c41-143">Nel campo **Gruppo di modelli di articoli** della Scheda dettaglio **Generale**, selezionare **DEF**.</span><span class="sxs-lookup"><span data-stu-id="47c41-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="47c41-144">Nel campo **Prezzo** della Scheda dettaglio **Acquisti**, digitare 10,00 come prezzo di costo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="47c41-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="47c41-145">Nel **riquadro azioni**, fare clic su **Gruppi di dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="47c41-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="47c41-146">Nel campo **Gruppo di dimensioni di immagazzinamento**, selezionare **Solo sito e magazzino**.</span><span class="sxs-lookup"><span data-stu-id="47c41-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="47c41-147">Nel campo **Gruppo di dimensioni di tracciabilità** selezionare **Nessuna dimensione di tracciabilità attiva**.</span><span class="sxs-lookup"><span data-stu-id="47c41-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="47c41-148">Creare un ordine fornitore per 10 pezzi dell'articolo Test a 6,00 per pezzo, quindi registrare una fattura per l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="47c41-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="47c41-149">Creare un secondo ordine fornitore per 10 pezzi dell'articolo Test a 8,00 per pezzo, quindi registrare una fattura per l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="47c41-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="47c41-150">Registrare una fattura per un ordine cliente per la vendita di cinque pezzi dell'articolo Test.</span><span class="sxs-lookup"><span data-stu-id="47c41-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="47c41-151">In questo caso, la riga ordine cliente è preventivata a 35,00 (5 pezzi \* costo medio di 7,00 per pezzo).</span><span class="sxs-lookup"><span data-stu-id="47c41-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="47c41-152">Creare un ordine di reso per il cliente.</span><span class="sxs-lookup"><span data-stu-id="47c41-152">Create a return order for the customer.</span></span> <span data-ttu-id="47c41-153">Nel modulo **Trova ordine cliente** selezionare la riga fattura, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47c41-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="47c41-154">Nel modulo **Ordine di reso - Codice NAR: %1, %2** verificare che un ordine di reso venga generato per il reso dell'articolo Test.</span><span class="sxs-lookup"><span data-stu-id="47c41-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="47c41-155">La quantità dell'ordine di reso è impostata su -5,00.</span><span class="sxs-lookup"><span data-stu-id="47c41-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="47c41-156">Il campo **ID lotto resi** visualizza un ID lotto.</span><span class="sxs-lookup"><span data-stu-id="47c41-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="47c41-157">Questo ID lotto viene ricavato dall'ordine cliente originale dell'articolo che è stato venduto al cliente.</span><span class="sxs-lookup"><span data-stu-id="47c41-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="47c41-158">Il campo **Prezzo di costo reso** visualizza il prezzo di costo dalla riga di vendita originale.</span><span class="sxs-lookup"><span data-stu-id="47c41-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="47c41-159">Registrare il ricevimento degli articoli resi.</span><span class="sxs-lookup"><span data-stu-id="47c41-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="47c41-160">Registrare un documento di trasporto per gli articoli resi.</span><span class="sxs-lookup"><span data-stu-id="47c41-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="47c41-161">Registrare una fattura per l'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="47c41-161">Post an invoice for the return order.</span></span> <span data-ttu-id="47c41-162">Nella pagina elenco **Tutti gli ordini cliente** selezionare un ordine cliente per cui **Ordine di reso** è il tipo di ordine.</span><span class="sxs-lookup"><span data-stu-id="47c41-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="47c41-163">Aprire il modulo **Operazioni di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="47c41-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="47c41-164">Verificare che il reso sia preventivato a 7,00 per pezzo utilizzando il valore nel campo **Prezzo di costo reso**, per un totale di 35,00 nel campo **Importo costi**.</span><span class="sxs-lookup"><span data-stu-id="47c41-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="47c41-165">È possibile aprire il modulo **Operazioni di magazzino** dal modulo **Ordine di reso - Codice NAR: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="47c41-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="47c41-166">Nella griglia **Righe** fare clic su **Magazzino** \> **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="47c41-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="47c41-167">In Gestione articoli e magazzino, utilizzare il modulo **Chiusura e rettifica** per eseguire la procedura **3. Chiudere**.</span><span class="sxs-lookup"><span data-stu-id="47c41-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="47c41-168">Questa azione consente di rettificare il costo nella riga di vendita originale, che era preventivata a -35,00 (5 pezzi \* 7,00), a -30,00 (5 pezzi \* 6,00).</span><span class="sxs-lookup"><span data-stu-id="47c41-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="47c41-169">Ciò accade perché il gruppo di modelli inventariali utilizza il metodo FIFO (First In, First Out) e 6,00 per pezzo è il costo FIFO dal primo ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="47c41-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="47c41-170">Inoltre, l'azione consente di rettificare il costo della riga di vendita di reso in modo che corrisponda al costo per pezzo nella riga di vendita originale.</span><span class="sxs-lookup"><span data-stu-id="47c41-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="47c41-171">Pertanto, il costo della riga di reso viene rettificato da 35,00 a 30,00.</span><span class="sxs-lookup"><span data-stu-id="47c41-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>




